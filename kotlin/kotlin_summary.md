# Kotlin Code Style Summary

## Использование библиотек

Under construction

## Оформление кода

### IDE's Code Style Settings

**Tabs and Indents**
* Tab size = `4`
* Indent = `4`
* Continuation indent = `4` *(default `8`)*

**Wrapping and Braces**
* Extends/implements list align when multiline = `true` *(default `false`)*

### Классы

#### Форматирование шапки класса

##### 1. Обычный класс
Шапка класса форматируется следующим образом:
```Kotlin
class SimpleClass {

    var someProperty: String = "I'm property!"

    fun someMethod() {
        println(someProperty)
    }
}
```

##### 2. Класс с одним значением или пропертей в конструкторе
Если в конструкторе класса присутствует 1 значение или пропертя, то она располагается на одной строке с кодовым словом **class**.
```kotlin
class SimpleClass(var someProperty: String) {

    fun someMethod() {
        println(someProperty)
    }
}
```

##### 3. Класс с более чем одним значением или пропертей в конструкторе
Если в конструкторе класса присутствует более 1 значения или пропертей, то они располагается друг под другом, начиная со следующей строки после строки с кодовым словом **class**.
```kotlin
class SimpleClass(
    var someProperty: String,
    val anotherProperty: Int) {

    fun someMethod() {
        println("$someProperty($anotherProperty)")
    }
}
```

##### 4. Наследование и имплементация

###### Наследование классов
Если в конструкторе класса потомка нет значений и пропертей, то родительский класс указывается на одной строке с кодовым словом **class**.
```kotlin
class SimpleClass : SuperSimpleClass() {

    fun someMethod() {
        // do something
    }
}
```
###### Класс с наследованием и реализацией интерфейсов
Интерфейсы, которые реализует класс-наследник, должны быть расположены друг под другом:
```kotlin
class SimpleClass : SuperSimpleClass(),
                    IFirst,
                    ISecond {

    fun someMethod() {
        // do something
    }
}
```
###### Класс с пропертями в конструкторе, наслодованием и реализацией интерфейсов
```kotlin
// Форматирование здорового человека
class MyClass(
    private var myProperty: Boolean,
    someProperty: String,
    anotherProperty: Int) : SimpleClass(someProperty, anotherProperty),
                            IFirst,
                            ISecond{

    override fun someMethod() {
        super.someMethod()
        println(myProperty)
    }
}

// Не делайте так, форматирование курильщика :(
class MyClass(
    private var myProperty: Boolean,
    someProperty: String,
    anotherProperty: Int
) : SimpleClass(someProperty, anotherProperty),
    IFirst,
    ISecond {

    override fun someMethod() {
        super.someMethod()
        println(myProperty)
    }
}

// Не делайте так, форматирование курильщика :(
class MyClass(
    private var myProperty: Boolean,
    someProperty: String,
    anotherProperty: Int
) : SimpleClass(someProperty, anotherProperty), IFirst, ISecond {

    override fun someMethod() {
        super.someMethod()
        println(myProperty)
    }
}
```

#### Расположение объекта компаньона

Объект компаньон располагается в самом низу класса
```kotlin
class ExampleActivity : AppCompatActivity() {

    private var somePropertie: String = ""
    private val anotherPropertie: Int = 20

    override fun onCreate(savedInstanceState: Bundle?, persistentState: PersistableBundle?) {
        super.onCreate(savedInstanceState, persistentState)
    }

    fun initViews() {
        // Doing some magic
    }

    companion object {
        const val EXAMPLE_KEY = "extra"
        const val MAX_COUNT_KEY = "extra"
        const val EXAMPLE_REQUEST_CODE = 100

        fun createIntent(): Intent {
            return Intent()
        }
    }
}
```

#### Декларирование однострочных методов
В ходе безжалостной схватки было решено, что единственно правильно всегда возвращать значение фукнции через кодовое слово **return**, игнорируя все прелести Котлина.
```kotlin
// Так должны выглядеть функции в нашей команде
fun providesCargoRepository(cargoApi: ICargoApi): ICargoRepository {
    return CargoRepository(cargoApi)
}

// Так Котлин развращает писать невинных девелоперов
fun providesCargoRepository(cargoApi: ICargoApi): ICargoRepository = CargoRepository(cargoApi)

fun providesCargoRepository(cargoApi: ICargoApi) = CargoRepository(cargoApi)
```

### Условия

#### Условие с телом любой длины (не относится к Guard statements)
Так как фигурные скобки бесплатные, то нам не жалко всегда заключать тело условий в красивые фигурные скобки. А бонусом они повышают читабильность кода :3
```kotlin
// Делай так ^_^
if (someTest) {
    doSomething()
}

// И так делай тоже :)
if (someTest) {
    doSomething()
} else {
    doSomethingElse()
}

// Но вот так лучше не делать :<
if (someTest) doSomething()

if (someTest) doSomething() else doSomethingElse()

if (someTest)
    doSomething()
else
    doSomethingElse()
```

#### Guard statements
Guard Statement помогает нам быстро убежать из функции, если что-то пошло не так. Поэтому мы хотим видеть его на одной строчке. Если быстро убежать не получается, то не стесняемся применять фигурные скобочки :)
```kotlin
// Быстро проверили на null и убежали - красота
fun example(nullableArg: String?) {
    if (nullableArg == null) return

    doSomething()
}

// А вот тут уже неправильно!
fun example(nullableArg: String?) {
    if (nullableArg == null)
        return

    doSomething()
}

// И так тоже неправильно :(
fun example(nullableArg: String?) {
    if (nullableArg == null) {
        return
    }

    doSomething()
}
```

#### Возвращение результата условия в переменную или из функции
Kotlin позволяет получать результат из операторов `if` и `when`.
А еще из Котлина убрали тернарный оператор, поэтому мы заменяем его оператором `if`.
```kotlin
// Фигачим все в одну строку как-будто это тернарный оператор ^_^
val colorRes = if(someTest) R.color.abc_color_highlight_material else R.color.cardview_shadow_end_color

// Если добавить переносы, то выглядит уже не так правильно
val colorRes = if(someTest)
    R.color.abc_color_highlight_material
else
    R.color.cardview_shadow_end_color

// И даже фигурные скобочки не могут вернуть элегантность
val colorRes = if(someTest) {
    R.color.abc_color_highlight_material
} else {
    R.color.cardview_shadow_end_color
}
```

### Лямбда функции

#### Вынесение лямбда функций за скобки
В Котлине, если последний параметр функции это функция и когда в качестве этого параметра передается лямбда выражение, есть возможность вынесения лямбда выражения за круглые скобки функции. Выглядит очень классно, поэтому мы активно этим пользуемся.
Для примера, у нас есть класс `SimpleClass`, у которого проперти это функция и у нас есть глобальная функция `doIfSdk`, у которого последний параметр это функция.
```Kotlin
class SimpleClass(val block: () -> Unit) {

   fun callBlock() {
       block.invoke()
   }
}


fun doIfSdk(version: Int, block: () -> Unit) {
   if (version >= BuildConfig.VERSION_CODE) {
       block.invoke()
   }
}
```

```Kotlin
// Форматирование у нас должно быть как в следующей фукнции:
fun outside() {
    val simpleObject = SimpleClass {
        /*do something*/
    }

    val simpleBigObject = SimpleClass {
        /* do
        something
        big */
    }

    doIfSdk(21) { /*do something*/ }

    doIfSdk(21) {
        /* do
        something
        big */
    }
}

// И ни в коем случае не такое как в этой
fun inside() {
    val simpleObject = SimpleClass({ /*do something*/ })

    val simpleBigObject = SimpleClass({
        /* do
        something
        big */
    })

    doIfSdk(21, { /*do something*/ })

    doIfSdk(21, {
        /* do
        something
        big */
    })
}
```

#### Вынесение тела лямбда функции
В нашей команде решили не заморачиваться с правилами насчет максимальной длины тела лямбда функции. Решили только руководствоваться здравым смыслом и выносить куски по мере необходимости.

#### Лямбда функции без параметров
Лямбда функции без параметров (`(() -> Unit)`) решили по возможности писать в одну строку.
```kotlin
// Вот так вот:
button.onClick { oneAction() }

button.onClick {
    firstAction()
    secondAction()
}

// А не вот так:
button.onClick {
    oneAction()
}
```

#### Лямбда функции с одним параметром и одним действием в теле
В лямбда функциях с одним параметром решили не злоупотреблять `it` и всегда явно указывать параметр. Для повышения читабильности мы так же переносим тело функции на следующую от параметра строку.
```kotlin
// Вот так короч надо
function { result ->
    showResult(result)
}

// А вот так лучше не надо
function {
    result ->
    showResult(result)
}

// Вот так точно не стоит
```kotlin
function { result -> showResult(result) }
```
```

#### Лямбда функции с одним параметром и несколькими действиями в теле

#### Лямбда функции с несколькими параметрами и одним действием в теле

#### Лямбда функции с несколькими параметрами и несколькими действиями в теле
