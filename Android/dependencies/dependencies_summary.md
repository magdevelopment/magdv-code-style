# Dependecies

### RxJava's Kotlin Extensions
https://github.com/ReactiveX/RxKotlin [Docs]

Из библиотеки в проектах используем:
* `plusAssign`

```Kotlin
// Для сборки всех подписок в одну коллекцию используем "+="
import io.reactivex.rxkotlin.plusAssign

subscriptions += interactor.request(params)
                .subscribe()


// А не "add"
subscriptions.add(interactor.request(params)
                .subscribe())


// Иногда можно "addTo", если подписку нужно сохранить отдельно, например
import io.reactivex.rxkotlin.addTo

val subscription = interactor.request(params)
                .subscribe()
                .addTo(subscriptions)

```
* `Iterable.toObservable`

```Kotlin
val collection: Iterable<String> = ArrayList()

// Делаем так
collection.toObservable()
    .subscribe()

// А не так
Observable.fromIterable(collection)
    .subscribe()
```

### Kotlin Android Extensions Plugin
https://kotlinlang.org/docs/tutorials/android-plugin.html [Docs]

Используем в проектах

### Anko
https://github.com/Kotlin/anko/wiki [Docs]

Используем в проектах фичи из Anko-common пакета
