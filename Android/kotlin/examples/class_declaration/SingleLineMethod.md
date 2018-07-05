# Single Line Method declaration

##### Single line
```kotlin
class Example {

    fun providesCargoRepository(cargoApi: ICargoApi): ICargoRepository = CargoRepository(cargoApi, CargoCache())

    //OR without return type

    fun providesCargoRepository(cargoApi: ICargoApi) = CargoRepository(cargoApi, CargoCache())

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
