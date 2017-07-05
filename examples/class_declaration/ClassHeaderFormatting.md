# Class Headers Formatting

According to [Official Kotlin coding conventions](https://kotlinlang.org/docs/reference/coding-conventions.html) with modifications

#### IDE Kotlin Code Style Setup

**Tabs and Indents**
* Tab size = `4`
* Indent = `4`
* Continuation indent = `4` *(default `8`)*

**Wrapping and Braces**
* Extends/implements list align when multiline = `true` *(default `false`)*


#### 1. Simple Class
```Kotlin
class SimpleClass {

    var someProperty: String = "I'm property!"

    fun someMethod() {
        println(someProperty)
    }
}
```

#### 2. Simple Class with one property in constructor
```kotlin
class SimpleClass(var someProperty: String) {

    fun someMethod() {
        println(someProperty)
    }
}
```

#### 3. Simple Class with two or more properties in constructor
```kotlin
class SimpleClass(
    var someProperty: String,
    val anotherProperty: Int) {

    fun someMethod() {
        println("$someProperty($anotherProperty)")
    }
}
```

#### 4. Extending and Implementation

Class extending
```kotlin
class SimpleClass : SuperSimpleClass() {

    fun someMethod() {
        // do something
    }
}
```
Class extending with interface implementations
```kotlin
class SimpleClass : SuperSimpleClass(),
                    IFirst,
                    ISecond {

    fun someMethod() {
        // do something
    }
}
```
Class extending with properties in constructor and interface implementations
```kotlin
class MyClass(
    private var myProperty: Boolean,
    someProperty: String,
    anotherProperty: Int) : SimpleClass(someProperty, anotherProperty),
                            IFirst,
                            ISecond{

    override fun someMethod() {
        super.someMethod()
        println(myProperty)
    }
}
```
