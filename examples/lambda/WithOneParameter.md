# Declaring Lambda with one parameter


### Function with one line body
#### With declaring parameter
###### Parameter at the same line with function and body at another one
```kotlin
function { result ->
    showResult(result)
}
```
###### Parameter on the second line of function and body at another one
```kotlin
function {
    result ->
    showResult(result)
}
```
###### Parameter and body on same line as function
```kotlin
function { result -> showResult(result) }
```
#### Without declaring parameter
###### Body on another line
```kotlin
function {
    showResult(it)
}
```
###### Body on the same line
```kotlin
function { showResult(it) }

```
###### Using method reference when possible
```kotlin
// Possible
function(this::showResult)

// When need map
function { showResult(it.toString()) }
```
