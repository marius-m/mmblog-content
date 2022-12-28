A set of utility methods that can be used in `Kotlin` or `Java`.

-   Main reason why I use this, is to **provide info on what class instance was used**.
-   Quite commonly I attach it to the caller itself, to figure out who executed the function. As this is quite standardised, it is quite easy to **filter out the results**.
-   This also works very well, when mutliple objects generate same message, as this class prints out the hex for the object. So it is **visible, that the object is different for each message**.

When it comes to **backtracing your app / service, it is all about the logs and their verbosity**. Project maintenance hangs on it.

**Usage samples**.

-   **Ex. 1**. Appending instance to message with instance where it is used.
    
    ```kotlin
    logger.info("onInit(app: $app)".withLogInstance(this))
    ```

[Source](https://gist.github.com/marius-m/f510e2dbbdf3c881e991ef2c139d1a6d)

```kotlin
/**
 * Debugging utils
 */
object LogUtils {

    /**
     * Converts [obj] to instance signature
     * Easier to figure out different object instance usage in combination to logging
     */
    @JvmStatic
    fun asStringInstance(obj: Any?): String {
        return if (obj != null) {
            String.format(
                "[%s@%s]",
                obj.javaClass.simpleName,
                Integer.toHexString(obj.hashCode())
            )
        } else "[null@instance]"
    }

    @JvmStatic
    fun asStringInstance(klass: KClass<*>, obj: Any?): String {
        return if (obj != null) {
            String.format(
                "[%s@%s]",
                klass.simpleName,
                Integer.toHexString(obj.hashCode())
            )
        } else "[null@instance]"
    }

    @JvmStatic
    private fun objMessage(klass: KClass<*>, obj: Any?, message: String): String {
        return String.format("%s: %s", asStringInstance(klass, obj), message)
    }

    @JvmStatic
    private fun objMessage(obj: Any?, message: String): String {
        return String.format("%s: %s", asStringInstance(obj), message)
    }

    fun String.withLogInstance(obj: Any?): String {
        return objMessage(obj, this)
    }

    fun String.withKLogInstance(klass: KClass<*>, obj: Any?): String {
        return objMessage(klass, obj, this)
    }

    fun String.withLogClass(klass: Class<*>): String {
        return String.format("[%s]: %s", klass.simpleName, this)
    }

    fun String.withLogKlass(klass: KClass<*>): String {
        return String.format("[%s]: %s", klass.simpleName, this)
    }
}
```