# Описание тела лямбда функций

###### 1) Всегда пишем все тело независимо от содержания
```kotlin
// Pofig :D
function {
    doShort()

    if (isTest) {
        doShort()
        doSomethingWithNormalName()
    } else {
        doAnotherShort()
        doThisAdvancedFlexibleThingWithReallyLongNameAsync()
    }

    function {
        doShort()
        doSomeShort()
    }
}
```
###### 2) Всегда пишем все тело независимо от длины если оно на одном уровне, при появлении нового уровня (условие, цикл, итд...), выносим в отедльный метод (с некоторыми исключениями в виде extensions `apply`, `let`, `with`, `buildString`, итд)
```kotlin
// OK ^_^
function {
    doShort()
    doAnotherShort()
    doAnotherShortAlso()
    doSomethingWithNormalName()
    doThisAdvancedFlexibleThingWithReallyLongNameAsync()
}

// Bad :c
function {
    if (isTest) {
        doSomeShort()
    }
}
```
###### 3) Выносим в отдельный метод как только количество строк превышает N (где N - договориться, например 3)
```kotlin
// OK :3
function {
    doShort()
    doSomethingWithNormalName()
    doThisAdvancedFlexibleThingWithReallyLongNameAsync()
}

// OK :)
function {
    list.forEach {
        doShort()
    }
}

// Bad :c
function {
    doShort()
    doAnotherShortAlso()
    doSomethingWithNormalName()
    doThisAdvancedFlexibleThingWithReallyLongNameAsync()
}
```
###### 4) Выносим в отдельный метод как только количество строк превышает N или появляется новый уровень
```kotlin
// OK :3
function {
    doShort()
    doSomethingWithNormalName()
    doThisAdvancedFlexibleThingWithReallyLongNameAsync()
}

// Bad :c
function {
    list.forEach {
        doShort()
    }
}

// Bad :c
function {
    doShort()
    doAnotherShortAlso()
    doSomethingWithNormalName()
    doThisAdvancedFlexibleThingWithReallyLongNameAsync()
}
```
