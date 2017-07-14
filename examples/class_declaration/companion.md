# Companion object

##### At the beginning of its wrapper class
```kotlin
class ExampleActivity : AppCompatActivity() {

    companion object {
        const val EXAMPLE_KEY = "extra"
        const val MAX_COUNT_KEY = "extra"
        const val EXAMPLE_REQUEST_CODE = 100

        fun createIntent(): Intent {
            return Intent()
        }
    }

    private var somePropertie: String = ""
    private val anotherPropertie: Int = 20

    override fun onCreate(savedInstanceState: Bundle?, persistentState: PersistableBundle?) {
        super.onCreate(savedInstanceState, persistentState)
    }

    fun initViews() {

    }
}
```

##### At the ending of its wrapper class
```kotlin

```
