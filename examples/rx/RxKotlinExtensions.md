# Using of RxKotlin Extensions

https://github.com/ReactiveX/RxKotlin [docs]

**1. Using PlusAssign**

Without `plusAssign`:
```kotlin
import io.reactivex.rxkotlin.plusAssign

subscriptions.add(interactor.request(params)
                .doOnSubscribe { viewState.showProgress() }
                .doFinally { viewState.hideProgress() }
                .subscribe())
```


With `plusAssign`:
```kotlin
import io.reactivex.rxkotlin.plusAssign

subscriptions += interactor.request(params)
                .doOnSubscribe { viewState.showProgress() }
                .doFinally { viewState.hideProgress() }
                .subscribe()
```

**2. Using SubscribeBy method with named arguments**

Without `SubscribeBy`:
```kotlin
Observable.just(1).subscribe(
                {
                    // do OnNext
                },
                {
                    // do OnError
                },
                {
                    // do OnComplete
                }
        )

        Single.just(1).subscribe(
                {
                    // do OnSuccess
                },
                {
                    // do OnError
                }
        )

        Completable.complete().subscribe(
                {
                    // do OnComplete
                },
                {
                    // do OnError
                }
        )
```

With `SubscribeBy`:
```kotlin
Observable.just(1).subscribeBy(
                onNext = {
                    // do OnNext
                },
                onError = {
                    // do OnError
                },
                onComplete = {
                    // do OnComplete
                }
        )

        Single.just(1).subscribeBy(
                onSuccess = {
                    // do OnSuccess
                },
                onError = {
                    // do OnError
                }
        )

        Completable.complete().subscribeBy(
                onComplete = {
                    // do OnComplete
                },
                onError = {
                    // do OnError
                }
        )
```

**3. Using Iterable.toObservable extension**

Without `Iterable.toObservable`
```kotlin
val list = listOf(1, 2, 3, 4, 5, 6)

Observable.fromIterable(list)
        .filter { it != 1 && it != 2 }
        .map { it.toString() }
        .toList()
        .subscribe(
                { numbers ->
                    // show numbers
                },
                {
                    // do OnError
                }
        )
```

With `Iterable.toObservable`
```kotlin
val list = listOf(1, 2, 3, 4, 5, 6)

list.toObservable()
        .filter { it != 1 && it != 2 }
        .map { it.toString() }
        .toList()
        .subscribe(
                { numbers ->
                    // show numbers
                },
                {
                    // do OnError
                }
        )
```
