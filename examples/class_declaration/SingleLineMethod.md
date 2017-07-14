# Single Line Method declaration

##### Single line
```kotlin
class Example {

    fun providesCargoRepository(cargoApi: ICargoApi): ICargoRepository = CargoRepository(cargoApi, CargoCache())

}
```

##### Default
```kotlin
class Example {

    fun providesCargoRepository(cargoApi: ICargoApi): ICargoRepository {
        return CargoRepository(cargoApi, CargoCache())
    }
}
```
