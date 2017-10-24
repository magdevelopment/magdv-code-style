# Dependecies

### RxJava's Kotlin Extensions
https://github.com/ReactiveX/RxKotlin [Docs]

В проектах используем `plusAssign` и `Iterable.toObservable` фичи из библиотеки.
```Kotlin
// Используем +=
import io.reactivex.rxkotlin.plusAssign

subscriptions += interactor.request(params)
                .doOnSubscribe { viewState.showProgress() }
                .doFinally { viewState.hideProgress() }
                .subscribe()

// Вместо add
subscriptions.add(interactor.request(params)
                .doOnSubscribe { viewState.showProgress() }
                .doFinally { viewState.hideProgress() }
                .subscribe())

```

### Kotlin Android Extensions Plugin
https://kotlinlang.org/docs/tutorials/android-plugin.html [Docs]

Используем в проектах

### Anko
https://github.com/Kotlin/anko/wiki [Docs]

Используем в проектах фичи из Anko-common пакета
