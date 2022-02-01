# Tinkering around Gradle plugin basics

From time to time, I get to touch something cool and unusual. This time I got to touch Gradle plugins, which I don&rsquo;t usually do, apart from applying to the project or configuring it by its extensions. I&rsquo;m pretty sure I am not the only one with this case scenario.


# TLDR;

Short story of how can you update / develop / tinker on already created Gradle plugin and bend it to your needs. You&rsquo;ll find brief intro how to

-   Build / develop Gradle plugin
-   Import locally built plugin into your project with your changes applied
-   Brief overview of important components to know in developing a Gradle plugin


# Backstory or just <span class="underline">why</span>

Here&rsquo;s what we were aiming for. We are automating our projects using [Appium](https://appium.io/). And we have decided to run the tests on a device farm. After a bit of investigation, we have decided to use [BrowserStack](https://www.browserstack.com/).

But to run the tests on the latest app, we need to upload the APK artifact for the device farm to find. So this is our first challenge - **upload the app to an app-automate server**.

Luckily enough, there&rsquo;s already a [BrowserStack plugin](https://github.com/browserstack/browserstack-gradle-plugin) that does this. However, as *most things are too good to be true*, we have the same situation here. It does only half of the job. It uploads the app to the app-testing server. But the plugin is open source, which means there&rsquo;s a possibility to update it ourselves.


# Rolling up the sleeves

This is where the fun part begins.

First off, I would like to mention that I did have an opportunity to write a few plugins in my time. However, I would *hardly call myself knowing what I&rsquo;m doing*. At the very least most of the time. Just plain trial and error. Even so, I&rsquo;m pretty sure there are some bits here that will be useful in the future for myself as well.


## Integrating the plugin

Updating the plugin is not so different from just applying the plugin regularly. Let&rsquo;s try that first.

-   First off, we need to provide the path where the plugin is located first. So in `{rootProject}/build.gradle` file, let&rsquo;s add a source and a path.

```
buildscript {
  repositories {
    maven {
      url "https://plugins.gradle.org/m2/"
    }
  }
  dependencies {
    classpath "gradle.plugin.com.browserstack.gradle:browserstack-gradle-plugin:3.0.3"
  }
}
```

-   Then we need to apply the plugin. That is normally done in project module - `{rootProject}/app/build.gradle` file

```
 apply plugin: "com.browserstack.gradle"
```

-   After integration, I like to check if everything synchronizes and works. My go-to command to check if the plugin has any public commands is `./gradlew tasks`, which list all the tasks. Chance is, you&rsquo;ll probably find a few tasks from the plugin there as well.


## Building the plugin

Now that we know the plugin is working let&rsquo;s try updating it.

My go-to method here is to **fork the original project**. That way, <span class="underline">if we apply our changes, it is easy to contribute those changes back to the main project</span> by creating a pull request.

After we clone the project, we could try to build it first. Generally, to build any project with the [Gradle build system](https://gradle.org/) is to use `./gradlew build`.

You can import the plugin as a regular project into [IntelliJ](https://www.jetbrains.com/idea/) as well. It&rsquo;ll be easier to develop.

As a side note, there&rsquo;s one neat trick. If the project does not have a [Gradle wrapper](https://docs.gradle.org/current/userguide/gradle_wrapper.html), you can generate it by running task `gradle wrap` if you have a Gradle installed. If you don&rsquo;t have Gradle installed, you can always use [Homebrew](https://brew.sh/) to [easily install it](https://formulae.brew.sh/formula/gradle) by running `brew install gradle`.

Have you managed to build it? Fingers crossed you did 🤞. If not, you can always try

-   Using older / different Gradle version
-   Checking out older branches that buildsb


## Integrating a local config

As we have the plugin built on our system, we could try <span class="underline">applying it to our project</span>.

After plugin builds, it generates a `jar` file, which we will use in our app project from before ☝️. Most commonly, after building the plugin, the jar file will be located in `{rootPlugin}/build/libs`. So in my case, it was `{rootPlugin}/build/libs/browserstack-gradle-plugin-3.0.3-u3x.jar`.

Now we need to update the project, so that the project would use our locally editable plugin, instead of the official repository.

-   First off, lets <span class="underline">change the dependency path to use our local computer path instead of remote path</span>

```
buildscript {
    repositories {
        // Original plugin: https://mvnrepository.com/artifact/gradle.plugin.com.browserstack.gradle/browserstack-gradle-plugin/3.0.3
        flatDir { dirs "/Users/mm/Projects/random/browserstack-gradle-plugin/build/libs" }
    }
    dependencies {
        classpath ":browserstack-gradle-plugin-3.0.3-u3x"
    }
}
```

-   To specify a directory, we use `flatDir`
-   We are specifying a directory where `.jar` file is built after we run a build task on a plugin
-   The `classpath` part **starts with a semicolon** - &ldquo;:&rdquo;
-   The `classpath` is a **file name of the generated directory without an extension**. So if I have a generated file `{rootPlugin}/build/libs/browserstack-gradle-plugin-3.0.3-u3x.jar`, I would need to provide a `:browserstack-gradle-plugin-3.0.3-u3x` classpath.
-   To apply the plugin, it is done the same as before. Apply `apply plugin: "com.browserstack.gradle"` in `{rootProject}/app/build.gradle`


## Updating the plugin

Now that we have everything set up, you can try to update the plugin, build it and run it on a project to see the changes.

Essentially the plugin is a regular project with a bit specific structure in how things are applied. The key points of interest are these.

-   Main plugin class. This is the main class where plugin starts its work. You could find it by searching for a class that `implements Plugin<Project>` and overrides a `public void apply(Project project)` method. This is where all work begins.
-   To provide properties from a project, you would need to use a component called [extensions](https://docs.gradle.org/current/userguide/custom_plugins.html#sec:mapping_extension_properties_to_task_properties). This is a regular [POJO](https://www.edureka.co/blog/pojo-in-java/) class however, to get properties from it, you&rsquo;ll need to use `project.getExtensions()`
-   The project will not recognize a plugin unless it has a special property file with essential information. I had a lot of trouble with this, so be sure to check out `{rootPlugin}/src/main/resources/META-INF.gradle.plugins/com.browserstack.gradle.properties` on a working project. **The directory/file naming is important here**.
-   Gradle works using tasks. So to find those, you&rsquo;ll need to keep an eye for `extends DefaultTask` or something similar. Also, you&rsquo;ll need to register those tasks to the plugin as well to be recognized - `project.getTasks().create("execute" + appVariantName + "TestsOnBrowserstack", EspressoTask.class...`

After you change the plugin, **build the plugin, then try to build the project you&rsquo;re using the plugin in**. It should synchronize the project and see the changes that you have applied for the plugin.


# The end result

After a few tries, I&rsquo;ve managed to provide a [few new features which were essential to our use case](https://github.com/marius-m/browserstack-gradle-plugin). Moreover, I&rsquo;ve managed to create a pull request to [give it back](https://github.com/browserstack/browserstack-gradle-plugin/pull/43) to the open source community. And last but not least, create an example (this blog post) that **it is actually not so hard to improve the project, by solving our own pains**. In other words, **open-source for the win** 🚀.

And most important, I have not have had so much fun in a long time 🧁.
