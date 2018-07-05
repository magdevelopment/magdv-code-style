# Conditional statements

### Function calling conditional
###### Single line when possible
```kotlin
if (someTest) doSomething()

if (someTest) doSomething() else doSomethingElse()

if (someTest) {
    doSomething()
    doSomethingElse()
}

if (someTest) {
    doSomething()
    doSomething()
} else {
    doSomethingElse()
}
```
###### Two lines not enclosed with braces when possible
```kotlin
if (someTest)
    doSomething()

if (someTest)
    doSomething()
else
    doSomethingElse()

if (someTest) {
    doSomething()
    doSomethingElse()
}

if (someTest) {
    doSomething()
    doSomething()
} else {
    doSomethingElse()
}
```
###### Always required to be enclosed with braces
```kotlin
if (someTest) {
    doSomething()
}

if (someTest) {
    doSomething()
} else {
    doSomethingElse()
}

if (someTest) {
    doSomething()
    doSomethingElse()
}

if (someTest) {
    doSomething()
    doSomething()
} else {
    doSomethingElse()
}
```

### Guard statements
###### Single line when possible
```kotlin
fun example(nullableArg: String?) {
    if (nullableArg == null) return

    doSomething()
}
```
###### Two lines not enclosed with braces when possible
```kotlin
fun example(nullableArg: String?) {
    if (nullableArg == null)
        return

    doSomething()
}
```
###### Two lines always enclosed with braces
```kotlin
fun example(nullableArg: String?) {
    if (nullableArg == null) {
        return
    }

    doSomething()
}
```
### Conditional result as variable
###### Single line when possible
```kotlin
val colorRes = if(someTest) R.color.abc_color_highlight_material else R.color.cardview_shadow_end_color
```
###### Two lines not enclosed with braces when possible
```kotlin
val colorRes = if(someTest)
    R.color.abc_color_highlight_material
else
    R.color.cardview_shadow_end_color
```
###### Two lines always enclosed with braces
```kotlin
val colorRes = if(someTest) {
    R.color.abc_color_highlight_material
} else {
    R.color.cardview_shadow_end_color
}
```
