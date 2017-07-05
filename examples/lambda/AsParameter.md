# Lambda as parameter or property

##### Explanation

In Kotlin, there is a convention that if the last parameter to a function is a function, and you're passing a lambda expression as the corresponding argument, you can specify it outside of parentheses.

For example we has a `SimpleClass` with function property and `doIfSdk` method with function parameter:
```Kotlin
class SimpleClass(val block: () -> Unit) {

    fun callBlock() {
        block.invoke()
    }
}


fun doIfSdk(version: Int, block: () -> Unit) {
    if (version >= BuildConfig.VERSION_CODE) {
        block.invoke()
    }
}
```

##### Example with lambda inside
```Kotlin
fun inside() {
    val simpleObject = SimpleClass({ /*do something*/ })

    val simpleBigObject = SimpleClass({
        /* do
        something
        big */
    })

    doIfSdk(21, { /*do something*/ })

    doIfSdk(21, {
        /* do
        something
        big */
    })
}
```

##### Example with lambda outside
```Kotlin
fun outside() {
    val simpleObject = SimpleClass {
        /*do something*/
    }

    val simpleBigObject = SimpleClass {
        /* do
        something
        big */
    }

    doIfSdk(21) { /*do something*/ }

    doIfSdk(21) {
        /* do
        something
        big */
    }
}
```
