Lately I got into a couple of interviews, that got *really* deep into technical questions. Either these questions are *actually* useful in actual inteviews is **really** up for debate. However I found them quite entertaining and interesting to know.

On the other hand, in some cases these may provide a bit of more insight for technical knowledge for a candidate. Or just simply, may be fun to use 🤷

In either case, here are my scribbles around them. Did not got around answering all of them. And in the deep of investigation, found other questions that may be used when interviewing.

I&rsquo;ll try to keep the list growing, will see how it goes 🤔


# Generic topics

Normally I don&rsquo;t really have a list of questions whenever I&rsquo;m going through an interview. Especially so due to its chaotic nature.

I do however have a list of topics that are a good reference to get a grasp of experience the candidate has.

This also works well, when preparing for a candidate in advance. Whenever going through a CV, LinkedIn you would naturally get some questions, that would expand on some of the *flavors* of these topics. In other works, it is a good reference.


## Topics

-   Libraries
    -   Serialization
    -   Networking
    -   State machine
    -   Dependency Injection
    -   Using something home grown
    -   Navigation frameworks
-   Infrastructure
    -   CI
    -   Code review
    -   Generate APK / Docker
    -   Git branching mechanism
-   Code style
    -   Composition over Inheritance
    -   SOLID Principles
        -   Single responsibility
        -   Open / Closed principle
        -   Liskov substitution
        -   Interface segregation
        -   Dependency inversion
        -   Mentioned &rsquo;single responsibility&rsquo;
        -   Floating around
    -   Sensitive data saving
    -   What types of tests can you perform?, (TDD, instrumentation, cut-off networking)
-   Tools
    -   Essential tools, IDE
    -   Proxy device?
    -   Dockerize environment?
    -   Use local dev server?
    -   Code automation from outside ?
    -   Keeping up with code style
-   People in work team
    -   How many people are working
    -   How do they share knowledge
-   Situational
    -   Unprepared API, figuring out how system work
    -   How to find screens that are used in the app
    -   Taking over a project, need to make a build
    -   How to align different styles of coding / different tools that are used
    -   Last difficult problem that you&rsquo;ve solved
    -   Collaboration with difficult colleague
-   Simple tech
    -   Where would you use a &rsquo;Service&rsquo;, &rsquo;Broadcast receiver&rsquo;
    -   What tools would you use if you would need to crate a network call and display results on screen (step by step)
    -   How do you pass data between activities
    -   Lifecycle events of an activity
    -   File structure of a project
        -   Translations
        -   Styles
        -   Code
    -   How do you create different types of the app (free, non-free)
    -   How would you communicate / pass data between fragments
    -   What are the differences between a list and a map
-   Medium / Harder tech
    -   Difference between Serializable / Parcelable, which one to use
    -   Can a &rsquo;Service&rsquo; interact directly with an &rsquo;Activity&rsquo;, how would you do it
    -   What is a singleton, what are the pros / cons, how would you do it
    -   Difference between `View` and `ViewGroup`
-   A bit random <code>[0%]</code>
    -   What are the most common resources that you use to keep up to date
    -   How to do you keep up-to-date? (tech wise)
    -   Biggest win, biggest failure?
    -   Most / least favorite tech
    -   Spare project
    -   Security ?
    -   Why not react native ar native?


# Questions

A very good and interesting list to know. However, as statet before, not entirely a good list to go through, when trying to &ldquo;get a feel&rdquo; how much experience a candidate has.

One idea where these questions would definitely work out, is probably, if the candidate is really good. Then these are excellent questions to &ldquo;press&rdquo; a bit.

Oh, and not all of the questions have an answer. Either I found the question interesting and didn&rsquo;t get a suitable answer for it, or I just simply don&rsquo;t know. Still though, it is good to get back to these questions, append more and keep the list growing.


## Generic questions <code>[7/21]</code>

-   [X] Exception types in java
    -   Checked Exceptions
    -   Unchecked Exceptions
-   [X] Solid principles
    -   The single-responsibility principle: &ldquo;There should never be more than one reason for a class to change.&rdquo; In other words, every class should have only one responsibility.
    -   The open–closed principle: &ldquo;Software entities &#x2026; should be open for extension, but closed for modification.&rdquo;
    -   The Liskov substitution principle: &ldquo;Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it.&rdquo;
    -   The interface segregation principle: &ldquo;Clients should not be forced to depend upon interfaces that they do not use.&rdquo;
    -   The dependency inversion principle: &ldquo;Depend upon abstractions, [not] concretions.&rdquo;
-   [ ] What are executors and what are used with
-   [ ] How maps work (buckets)
    -   Map doesn’t contain duplicate keys.
    -   Each key can map at max one value.
    -   [How maps work](http://coding-geek.com/how-does-a-hashmap-work-in-java/)
-   [X] Strings are immutable (Why strings are immuable)
    -   The collection of strings stored in the heap memory refers to the String pool. Whenever a new object is created, it is checked if it is already present in the String pool or not.
-   [ ] Kotlin `inline` / `crossinline`
-   [ ] Generics in java / kotlin
-   [-] Kotlin&rsquo;s `Any` object difference from `Object`
    -   [(Blog) Special classes in Kotlin](https://itnext.io/kotlin-basics-types-any-unit-and-nothing-674cc858035?gi=edf1c7e01348)
-   [ ] Equals + hashCode contract
    -   [Tutorial of equals](https://www.baeldung.com/java-equals-hashcode-contracts)
-   [ ] Kotlin&rsquo;s extension functions (what is it), how do you use it in Java?
-   [X] Why is it a bad idea to have arguments in constructor for `Fragment`
    -   Fragments uses default constructors to rebuild fragments
-   [ ] How to pass properties from `fragment` / `activity`
-   [ ] What is the difference between an `Activity` and `Fragment`
-   [ ] What is the difference between `ArrayList` and `LinkedList`
-   [X] What is the difference between `Array` and `List`
    -   Array
        -   Cannot contain values of different data types
        -   Size must be defined at the time of declaration
        -   Need to specify the index in order to add data
        -   Arrays are not type parameterized
        -   Arrays can contain primitive data types as well as objects
    -   List
        -   Can contain values of different data types.
        -   Size can be dynamically changed
        -   No need to specify the index
        -   Arraylists are type
        -   Arraylists can contain only objects, no primitive data types are allowed
-   [X] What is java reflection and where it is commonly used
    -   Most commonly used in deserializers
    -   Lets you access class model, its methods, change its access
-   [X] What are the differences between Heap and Stack Memory in Java?
    -   Stack
        -   **Memory** - Stack memory is used only by one thread of execution.
        -   **Access** - Stack memory can’t be accessed by other threads.
        -   **Memory Management** - Follows LIFO manner to free memory.
        -   **Lifetime** - Exists until the end of execution of the thread.
        -   **Usage** - Stack memory only contains local primitive and reference variables to objects in heap space.
    -   Heap
        -   **Memory** - Heap memory is used by all the parts of the application.
        -   **Access** - Objects stored in the heap are globally accessible.
        -   **Memory Management**- Memory management is based on the generation associated with each object.
        -   **Lifetime** - Heap memory lives from the start till the end of application execution.
        -   **Usage** - Whenever an object is created, it’s always stored in the Heap space.
-   [ ] Why `ViewModel` has a longer lifecycle than `Activity` / `Fragment`?
-   [ ] How to initialize coroutines?
-   [ ] What are the operators for `flatMap`, `concatMap`, `switchMap` (rx).
-   [ ] What is the difference and how do you use `observeOn` and `subscribeOn`


## Questions extra <code>[12/15]</code>

A few more of those extras.

-   [X] Explain different types of typecasting?
    -   Implicit: Storing values from a smaller data type to the larger data type. It is automatically done by the compiler.
    -   Explicit: Storing the value of a larger data type into a smaller data type. This results in information loss:
-   [X] Explain access modifiers in Java
    -   Default
    -   Private
    -   Protected
    -   Public
-   [X] Differentiate between `break` and `continue`
    -   Break
        -   Can be used in switch and loop (for, while, do while) statements
        -   It causes the switch or loop statements to terminate the moment it is executed
        -   It terminates the innermost enclosing loop or switch immediately
    -   Continue
        -   Can be only used with loop statements
        -   It doesn’t terminate the loop but causes the loop to jump to the next iteration
        -   A continue within a loop nested with a switch will cause the next loop iteration to execute
-   [X] Explain what are `static` methods and variables? How to they differ from object reference
    -   Static
        -   The static keyword must be used before the method name
        -   It is called using the class (className.methodName)
        -   They can’t access any non-static instance variables or methods
    -   Non-static
        -   No need to use the static keyword before the method name
        -   It is can be called like any general method
        -   It can access any static method and any static variable without creating an instance of the class
-   [X] Please explain Local variables and Instance variables in Java.
-   [X] Could you draw a comparison between `Array` and `ArrayList`?
    -   An array necessitates for giving the size during the time of declaration, while an array list doesn&rsquo;t necessarily require size as it changes size dynamically.
-   [X] Why do we use the `yield()` method?
    -   The yield() method belongs to the thread class. It transfers the currently running thread to a runnable state and also allows the other threads to execute. In other words, it gives equal priority threads a chance to run.
-   [X] What is Java autoboxing feature
    -   `int` vs `Integer`
-   [X] How does the `throw` keyword differ from the `throws` keyword?
    -   `throw` will throw an exception, `throws` defines a method to throw a checked exception
-   [X] Types of collections
    -   Classes – `ArrayList`, `LinkedList`, `Lists`, and `Vector`
    -   Interfaces – `Collection`, `List`, `Map`, `Queue`, `Set`, `SortedMap`, and `SortedSet`
    -   Maps – `HashMap`, `HashTable`, `LinkedHashMap`, and `TreeMap`
    -   Queues – `PriorityQueue`
    -   Sets – `HashSet`, `LinkedHashSet`, and `TreeSet`
-   [ ] What is `synchronized`
-   [X] Differentiate between `==` and `equals()` ?
    -   In java one checks for reference, another one for value comparement
    -   Also case can be ignored
    -   In kotlin, `==` uses the function itself ([link](https://kotlinlang.org/spec/expressions.html))
-   [X] What is the difference between a **local** variable and an **instance** variable5
    -   In Java, a local variable is typically used inside a method, constructor, or a block and has only local scope.
    -   Whereas, an instance variable in Java, is a variable which is bounded to its object itself.
-   [ ] How do you override static or private methods?
    -   You don&rsquo;t
-   [ ] How do you use flavors in Android, what are dimensions of a flavor


## Very tricky extra&rsquo;s <code>[2/2]</code>

Rally tricky ones, that are a bit wild west if a candidate might know it 🤷

-   [X] Explain the term &ldquo;Double Brace Initialization&rdquo; in Java?
    -   Double Brace Initialization is a Java term that refers to the combination of two independent processes. There are two braces used in this. The first brace creates an anonymous inner class. The second brace is an initialization block. When these both are used together, it is known as Double Brace Initialization. The inner class has a reference to the enclosing outer class, generally using the ‘this’ pointer. It is used to do both creation and initialization in a single statement. It is generally used to initialize collections. It reduces the code and also makes it more readable.
-   [X] Why is it said that the length() method of String class doesn’t return accurate results?
    -   The length() method of String class doesn’t return accurate results because it simply takes into account the number of characters within in the String. In other words, code points outside of the BMP (Basic Multilingual Plane), that is, code points having a value of U+10000 or above, will be ignored.
    -   The reason for this is historical. One of Java’s original goals was to consider all text as Unicode; yet, Unicode did not define code points outside of the BMP at the time. It was too late to modify char by the time Unicode specified such code points.


# Design patterns

As always, even if I use a pattern, I can never remember the name of it. So again - a good idea to refurbish patterns and their names.

-   [Res](https://refactoring.guru/design-patterns/creational-patterns)
-   **Creational**
    -   [Factory method](https://refactoring.guru/design-patterns/factory-method)
        -   Factory Method is a creational design pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.
    -   [Abstract factory](https://refactoring.guru/design-patterns/abstract-factory)
        -   Abstract Factory is a creational design pattern that lets you produce families of related objects without specifying their concrete classes.
    -   [Builder pattern](https://refactoring.guru/design-patterns/builder)
        -   Builder is a creational design pattern that lets you construct complex objects step by step.
    -   [Prototype](https://refactoring.guru/design-patterns/prototype)
        -   Lets you copy existing objects without making your code dependent on their classes.
        -   The pattern declares a common interface for all objects that support cloning. This interface lets you clone an object without coupling your code to the class of that object. Usually, such an interface contains just a single clone method.
    -   [Singleton pattern](https://refactoring.guru/design-patterns/singleton)
        -   Singleton is a creational design pattern that lets you ensure that a class has only one instance, while providing a global access point to this instance.
-   **Structural**
    -   [Adapter](https://refactoring.guru/design-patterns/adapter)
        -   Adapter is a structural design pattern that allows objects with incompatible interfaces to collaborate.
        -   Sample: XML -> JSON
    -   [Bridge](https://refactoring.guru/design-patterns/bridge)
        -   Bridge is a structural design pattern that lets you split a large class or a set of closely related classes into two separate hierarchies—abstraction and implementation—which can be developed independently of each other.
    -   [Composite](https://refactoring.guru/design-patterns/composite)
        -   Composite is a structural design pattern that lets you compose objects into tree structures and then work with these structures as if they were individual objects.
        -   The greatest benefit of this approach is that you don’t need to care about the concrete classes of objects that compose the tree. You don’t need to know whether an object is a simple product or a sophisticated box. You can treat them all the same via the common interface. When you call a method, the objects themselves pass the request down the tree.
    -   [Decorator](https://refactoring.guru/design-patterns/decorator)
        -   Decorator is a structural design pattern that lets you attach new behaviors to objects by placing these objects inside special wrapper objects that contain the behaviors.
        -   “Wrapper” is the alternative nickname for the Decorator pattern that clearly expresses the main idea of the pattern
    -   [Facade](https://refactoring.guru/design-patterns/facade)
        -   Facade is a structural design pattern that provides a simplified interface to a library, a framework, or any other complex set of classes.
        -   A facade is a class that provides a simple interface to a complex subsystem which contains lots of moving parts. A facade might provide limited functionality in comparison to working with the subsystem directly. However, it includes only those features that clients really care about.
    -   [Flyweight](https://refactoring.guru/design-patterns/flyweight)
        -   Flyweight is a structural design pattern that lets you fit more objects into the available amount of RAM by sharing common parts of state between multiple objects instead of keeping all of the data in each object.
    -   [Proxy](https://refactoring.guru/design-patterns/proxy)
        -   Proxy is a structural design pattern that lets you provide a substitute or placeholder for another object. A proxy controls access to the original object, allowing you to perform something either before or after the request gets through to the original object.
        -   The Proxy pattern suggests that you create a new proxy class with the same interface as an original service object. Then you update your app so that it passes the proxy object to all of the original object’s clients. Upon receiving a request from a client, the proxy creates a real service object and delegates all the work to it.
-   **Behavioral**
    -   [Chain of responsibility](https://refactoring.guru/design-patterns/chain-of-responsibility)
        -   Chain of Responsibility is a behavioral design pattern that lets you pass requests along a chain of handlers. Upon receiving a request, each handler decides either to process the request or to pass it to the next handler in the chain.
    -   [Command pattern](https://refactoring.guru/design-patterns/command)
        -   Command is a behavioral design pattern that turns a request into a stand-alone object that contains all information about the request. This transformation lets you pass requests as a method arguments, delay or queue a request’s execution, and support undoable operations.
    -   [Iterator](https://refactoring.guru/design-patterns/iterator)
        -   Iterator is a behavioral design pattern that lets you traverse elements of a collection without exposing its underlying representation (list, stack, tree, etc.).
    -   [Mediator](https://refactoring.guru/design-patterns/mediator)
        -   Mediator is a behavioral design pattern that lets you reduce chaotic dependencies between objects. The pattern restricts direct communications between the objects and forces them to collaborate only via a mediator object.
        -   The Mediator pattern suggests that you should cease all direct communication between the components which you want to make independent of each other. Instead, these components must collaborate indirectly, by calling a special mediator object that redirects the calls to appropriate components.
    -   [Memento](https://refactoring.guru/design-patterns/memento)
        -   Memento is a behavioral design pattern that lets you save and restore the previous state of an object without revealing the details of its implementation.
        -   The pattern suggests storing the copy of the object’s state in a special object called memento. The contents of the memento aren’t accessible to any other object except the one that produced it
    -   [Observer](https://refactoring.guru/design-patterns/observer)
        -   Also known as: Event-Subscriber, Listener
        -   Observer is a behavioral design pattern that lets you define a subscription mechanism to notify multiple objects about any events that happen to the object they’re observing.
    -   [State](https://refactoring.guru/design-patterns/state)
        -   State is a behavioral design pattern that lets an object alter its behavior when its internal state changes. It appears as if the object changed its class.
        -   The State pattern suggests that you create new classes for all possible states of an object and extract all state-specific behaviors into these classes.
        -   This structure may look similar to the Strategy pattern, but there’s one key difference. In the State pattern, the particular states may be aware of each other and initiate transitions from one state to another, whereas strategies almost never know about each other.
    -   [Strategy](https://refactoring.guru/design-patterns/strategy)
        -   Strategy is a behavioral design pattern that lets you define a family of algorithms, put each of them into a separate class, and make their objects interchangeable.
        -   The Strategy pattern suggests that you take a class that does something specific in a lot of different ways and extract all of these algorithms into separate classes called strategies.
    -   [Template method](https://refactoring.guru/design-patterns/template-method)
        -   Template Method is a behavioral design pattern that defines the skeleton of an algorithm in the superclass but lets subclasses override specific steps of the algorithm without changing its structure.
        -   The Template Method pattern suggests that you break down an algorithm into a series of steps, turn these steps into methods, and put a series of calls to these methods inside a single template method.
    -   [Visitor pattern](https://refactoring.guru/design-patterns/visitor)
        -   Visitor is a behavioral design pattern that lets you separate algorithms from the objects on which they operate.
        -   Since the objects know their own classes, they’ll be able to pick a proper method on the visitor less awkwardly. They “accept” a visitor and tell it what visiting method should be executed.


# IT Fundamentals and principles

Really just a set of various principles. It is just a good way to check and refurbish some ideas.

-   [Res](https://en.wikipedia.org/wiki/Category:Programming_principles)
-   Abstraction principle (computer programming)
    -   Reduce duplication
    -   DRY principle
-   Black box
    -   Hide implementation details under the interface (or its contract)
    -   Only the input and output can be assumed
-   Code reuse
    -   Code reuse may be achieved by different ways depending on a complexity of a programming language chosen and range from a lower-level approaches like code copy-pasting, simple functions or a bunch of objects or functions organized into modules
-   Cohesion
    -   degree to which the elements inside a module belong together
    -   high cohesion is associated with several desirable traits of software including robustness, reliability, reusability, and understandability.
    -   In contrast, low cohesion is associated with undesirable traits such as being difficult to maintain, test, reuse, or even understand.
-   Command–query separation
    -   It states that every method should either be a command that performs an action, or a query that returns data to the caller, but not both
    -   methods should return a value only if they are referentially transparent and hence possess no side effects.
-   Coupling
    -   is the degree of interdependence between software modules
-   Defensive programming
    -   intended to develop programs that are capable of detect potential security abnormalities and make predetermined response
    -   Making the software behave in a predictable manner despite unexpected inputs or user actions.
    -   Overly defensive programming, however, may safeguard against errors that will never be encountered, thus incurring run-time and maintenance costs
-   Dependency inversion principle
    -   When following this principle, the conventional dependency relationships established from high-level, policy-setting modules to low-level, dependency modules are reversed, thus rendering high-level modules independent of the low-level module implementation details
    -   High-level modules should not import anything from low-level modules. Both should depend on abstractions (e.g., interfaces).
    -   Abstractions should not depend on details. Details (concrete implementations) should depend on abstractions.
-   Deutsch limit
    -   The primitives in a visual language are the separate graphical elements used to build a program, and having more of them available at the same time allows the programmer to read more information.
-   Discoverabilty
    -   Discoverability is the degree to which something, especially a piece of content or information, can be found in a search of a file, database, or other information system.
-   Don&rsquo;t repeat yourself
    -   is a principle of software development aimed at reducing repetition of software patterns
    -   Another approach to abstractions is the AHA principle. AHA stands for &ldquo;Avoid Hasty Abstractions&rdquo;,
-   Fail fast
    -   Fail-fast systems are usually designed to stop normal operation rather than attempt to continue a possibly flawed process.
    -   Asserts?
    -   Throwing exception early
-   Gall&rsquo;s law
    -   A complex system designed from scratch never works and cannot be patched up to make it work. You have to start over with a working simple system
    -   &ldquo;agile software development&rdquo;
-   GRASP (object-oriented design)
    -   General Responsibility Assignment Software Patterns
    -   The different patterns and principles used in GRASP are controller, creator, indirection, information expert, low coupling, high cohesion, polymorphism, protected variations, and pure fabrication
-   Polymorphism
    -   Problem: How to handle alternatives based on type? How to create pluggable software components?
    -   Solution: When related alternatives or behaviors vary by type (class), assign responsibility for the behavior—using polymorphic operations—to the types for which the behavior varies. (Polymorphism has several related meanings. In this context, it means &ldquo;giving the same name to services in different objects&rdquo;.)
-   &ldquo;If it ain&rsquo;t broke, don&rsquo;t fix it&rdquo;
-   Information hiding
    -   the protection involves providing a stable interface which protects the remainder of the program from the implementation (whose details are likely to change)
    -   Encapsulation helps a lot
-   Interface segregation principle
    -   states that no code should be forced to depend on methods it does not use.
    -   ISP splits interfaces that are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them
    -   ISP is intended to keep a system decoupled and thus easier to refactor, change, and redeploy
    -   ISP is one of the five SOLID principles of object-oriented design
-   Inversion of control
    -   custom-written portions of a computer program receive the flow of control from a generic framework
    -   Inversion of control is used to increase modularity of the program and make it extensible
    -   The term is related to, but different from, the dependency inversion principle, which concerns itself with decoupling dependencies between high-level and low-level layers through shared abstractions
-   KISS principle
    -   KISS, an acronym for keep it simple stupid
    -   most systems work best if they are kept simple rather than made complicated
    -   Good sample is Linux system and its GNU tools
-   Law of Demeter
    -   In its general form, the LoD is a specific case of loose coupling
        -   Each unit should have only limited knowledge about other units: only units &ldquo;closely&rdquo; related to the current unit.
        -   Each unit should only talk to its friends; don&rsquo;t talk to strangers.
        -   Only talk to your immediate friends.
-   Liskov substitution principle
    -   a principle in object-oriented programming stating that an object (such as a class) and a sub-object (such as a class that extends the first class) must be interchangeable without breaking the program
    -   that is, if S is a subtype of T, then objects of type T in a program may be replaced with objects of type S without altering any of the desirable properties of that program
-   Loose coupling
    -   In which components are weakly associated (have breakable relationships) with each other, and thus changes in one component least affect existence or performance of another component.
    -   in which each of its components has, or makes use of, little or no knowledge of the definitions of other separate components
-   Ninety–ninety rule
    -   The first 90 percent of the code accounts for the first 90 percent of the development time. The remaining 10 percent of the code accounts for the other 90 percent of the development time
-   Offensive programming
    -   Rather, offensive programming adds an explicit priority of not tolerating errors in wrong places: the point where it departs from extreme interpretations of defensive programming is in preferring the presence of errors from within the program&rsquo;s line of defense to be blatantly obvious over the hypothetical safety benefit of tolerating them
    -   This preference is also what justifies using assertions
-   Open–closed principle
    -   should be open for extension, but closed for modification
    -   for instance, inheritance or delegate functions
-   Principle of least astonishment
    -   The principle of least astonishment (POLA), aka principle of least surprise
    -   It proposes that a component of a system should behave in a way that most users will expect it to behave.
    -   If a necessary feature has a high astonishment factor, it may be necessary to redesign the feature.
-   Pristine Sources
    -   Pristine Sources is a software management concept coined by the developers of the short-lived Bogus Linux distribution and popularized by Marc Ewing, co-founder of Red Hat Inc, after he adopted it and RPM Package Manager
    -   &ldquo;pristine&rdquo; - in its original condition; unspoil
    -   This is where the concept of pristine sources comes in. RPM has been designed to use the sources as they come from the application&rsquo;s developer, no matter how it has been packaged and configured. The main benefit is that the changes you as a package builder need to make, remain separate from the original sources, in a distinct collection of patches.
-   Rule of three
    -   It states that two instances of similar code do not require refactoring, but when similar code is used three times, it should be extracted into a new procedure.
-   Separation of concerns
    -   is a design principle for separating a computer program into distinct sections.
    -   Modularity, and hence separation of concerns, is achieved by encapsulating information inside a section of code that has a well-defined interface
    -   Layered designs in information systems are another embodiment of separation of concerns (e.g., presentation layer, business logic layer, data access layer, persistence layer)
-   Separation of mechanism and policy
    -   It states that mechanisms (those parts of a system implementation that control the authorization of operations and the allocation of resources) should not dictate (or overly restrict) the policies according to which decisions are made about which operations to authorize, and which resources to allocate.
-   Single-responsibility principle
    -   A module should be responsible to one, and only one, actor
    -   A class should have only one reason to change
-   SOLID
    -   The single-responsibility principle: &ldquo;There should never be more than one reason for a class to change.&rdquo; In other words, every class should have only one responsibility.
    -   The open–closed principle: &ldquo;Software entities &#x2026; should be open for extension, but closed for modification.&rdquo;
    -   The Liskov substitution principle: &ldquo;Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it.&rdquo;
    -   The interface segregation principle: &ldquo;Clients should not be forced to depend upon interfaces that they do not use.&rdquo;
    -   The dependency inversion principle: &ldquo;Depend upon abstractions, [not] concretions.&rdquo;
-   Uniform access principle
    -   states that there should be no syntactical difference between working with an attribute, pre-computed property, or method/query of an object
-   Worse is better
    -   also called the &rsquo;New Jersey style&rsquo;
    -   It refers to the argument that software quality does not necessarily increase with functionality: that there is a point where less functionality (&ldquo;worse&rdquo;) is a preferable option (&ldquo;better&rdquo;) in terms of practicality and usability
-   You aren&rsquo;t gonna need it
    -   YAGNI
    -   that states a programmer should not add functionality until deemed necessary
-   Zen of Python
    -   Beautiful is better than ugly.
    -   Explicit is better than implicit.
    -   Simple is better than complex.
    -   Complex is better than complicated.
    -   Flat is better than nested.
    -   Sparse is better than dense.
    -   Readability counts.
    -   Special cases aren&rsquo;t special enough to break the rules.
    -   Although practicality beats purity.
    -   Errors should never pass silently.
    -   Unless explicitly silenced.
    -   In the face of ambiguity, refuse the temptation to guess.
    -   There should be one– and preferably only one –obvious way to do it.[a]
    -   Although that way may not be obvious at first unless you&rsquo;re Dutch.
    -   Now is better than never.
    -   Although never is often better than right now.[b]
    -   If the implementation is hard to explain, it&rsquo;s a bad idea.
    -   If the implementation is easy to explain, it may be a good idea.
    -   Namespaces are one honking great idea – let&rsquo;s do more of those!
-   Zero one infinity rule
    -   It argues that arbitrary limits on the number of instances of a particular type of data or structure should not be allowed
    -   Specifically, an entity should either be forbidden entirely, only one should be allowed, or any number of them should be allowed.[2] Although various factors outside that particular software could limit this number in practice, it should not be the software itself that puts a hard limit on the number of instances of the entity.


# Development methodologies

Ah. The place of least experience. On one hand, I don&rsquo;t really invest time into it, as I don&rsquo;t really have too much work around it. But then again, it is always good to know the naming, if you will be looking for some of the things around that topic.

-   Most modern development processes can be vaguely described as agile. Other methodologies include waterfall, prototyping, iterative and incremental development, spiral development, rapid application development, and extreme programming.
-   &ldquo;Agile software development&rdquo; refers to a group of software development frameworks based on iterative development, where requirements and solutions evolve via collaboration between self-organizing cross-functional teams.
    -   Dynamic systems development method (DSDM)
    -   Kanban
        -   Kanban is a lean method to manage and improve work across human systems. This approach aims to manage work by balancing demands with available capacity, and by improving the handling of system-level bottlenecks.
        -   Work items are visualized to give participants a view of progress and process, from start to finish—usually via a kanban board. Work is pulled as capacity permits, rather than work being pushed into the process when requested.
    -   Scrum
        -   It is designed for teams of ten or fewer members who break their work into goals that can be completed within time-boxed iterations, called sprints, no longer than one month and most commonly two weeks. The scrum team assesses progress in time-boxed daily meetings of 15 minutes or fewer, called daily scrums. At the end of the sprint, the team holds two further meetings: one sprint review which demonstrates the work done for stakeholders to elicit feedback and one sprint retrospective which enables the team to reflect and improve.
    -   Crystal
    -   Atern
    -   Lean software development
        -   Eliminate waste
        -   Amplify learning
        -   Decide as late as possible
        -   Deliver as fast as possible
        -   Empower the team
        -   Build integrity in
        -   Optimize the whole
-   Continuous integration
    -   Continuous integration is the practice of merging all developer working copies to a shared mainline several times a day.[5] Grady Booch first named and proposed CI in his 1991 method,[6] although he did not advocate integrating several times a day. Extreme programming (XP) adopted the concept of CI and did advocate integrating more than once per day – perhaps as many as tens of times per day.
-   Incremental development
    -   Various methods are acceptable for combining linear and iterative systems development methodologies, with the primary objective of each being to reduce inherent project risk by breaking a project into smaller segments and providing more ease-of-change during the development process.
-   Rapid application development
    -   Rapid application development (RAD) is a software development methodology, which favors iterative development and the rapid construction of prototypes instead of large amounts of up-front planning.
-   Waterfall development
    -   The waterfall model is a sequential development approach, in which development is seen as flowing steadily downwards (like a waterfall) through several phases


# Architecture

Not much here 🤷

-   [(Blog) MVC, MVP, MVVM comaprement](https://academy.realm.io/posts/eric-maxwell-mvc-mvp-and-mvvm-on-android/)
