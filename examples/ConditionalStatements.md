# Conditional statements

##### Always required to be enclosed with braces
```kotlin
if (someTest) {
  doSomething()
}

if (someTest) { doSomethingElse() }

if (someTest) {
  doSomething()
  doSomething()
}
```
##### Not enclosed with braces for one action
```kotlin
if (someTest)
  doSomething()

if (someTest) doSomethingElse()

if (someTest) {
  doSomething()
  doSomething()
}
```
