# Declaring Lambdas with more than one parameters

### Function with one line body
###### Parameters at the same line with function and body at another one
```kotlin
fetchData { count, title ->
    setCountAndTitle(title, count)
}

// OR

fetchData { count, title ->

    setCountAndTitle(title, count)
}
```
###### Parameters each by each started from the line of function and body at another one
```kotlin
fetchData { count,
            title ->
    setCountAndTitle(title, count)
}

// OR

fetchData { count,
            title ->

    setCountAndTitle(title, count)
}
```
###### Parameters on the next line of function and body at another one
```kotlin
fetchData {
    count, title ->
    setCountAndTitle(title, count)
}

// OR

fetchData {
    count, title ->

    setCountAndTitle(title, count)
}
```
###### Parameters each by each started from the next line of function and body at another one
```kotlin
fetchData {
    count,
    title ->
    setCountAndTitle(title, count)
}

// OR

fetchData {
    count,
    title ->

    setCountAndTitle(title, count)
}
```
###### Parameters and body on same line as function
```kotlin
fetchData { count, title -> setCountAndTitle(title, count) }
```

### Function with multiline body
###### Parameters at the same line with function and body at another one
```kotlin
fetchData { count, title ->
    setCount(count)
    setTitle(title)
}

// OR

fetchData { count, title ->

    setCount(count)
    setTitle(title)
}
```
###### Parameters each by each started from the line of function and body at another one
```kotlin
fetchData { count,
            title ->
    setCount(count)
    setTitle(title)
}

// OR

fetchData { count,
            title ->

    setCount(count)
    setTitle(title)
}
```
###### Parameters on the next line of function and body at another one
```kotlin
fetchData {
    count, title ->
    setCount(count)
    setTitle(title)
}

// OR

fetchData {
    count, title ->

    setCount(count)
    setTitle(title)
}
```


###### Parameters each by each started from the next line of function and body at another one
```kotlin
fetchData {
    count,
    title ->
    setCount(count)
    setTitle(title)
}

// OR

fetchData {
    count,
    title ->

    setCount(count)
    setTitle(title)
}
```
