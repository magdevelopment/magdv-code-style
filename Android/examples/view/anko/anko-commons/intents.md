# Using of Anko Commons Intents

##### Simple Intent for activity
```kotlin
// Without Anko-commons
fun createIntent(context: Context): Intent {
    return Intent(context, SimpleActivity::class.java)
}

// With Anko-commons
fun createIntent(context: Context): Intent {
    return context.intentFor<SimpleActivity>()
}
```

##### Intent for activity with one extra
```kotlin
// Without Anko-commons
fun createIntent(context: Context, searchQuery: String): Intent {
    val intent = Intent(context, ExampleActivity::class.java)
    intent.putExtra(ExampleActivity.SEARCH_KEY, searchQuery)
    return intent
}

// With Anko-commons
fun createIntent(context: Context, searchQuery: String): Intent {
    return context.intentFor<ExampleActivity>(ExampleActivity.SEARCH_KEY to searchQuery)
}
```

##### Intent for activity with two or more extras
```kotlin
// Without Anko-commons
fun createIntent(context: Context, searchQuery: String, maxCount: Int): Intent {
    val intent = Intent(context, ExampleActivity::class.java)
    intent.putExtra(ExampleActivity.SEARCH_KEY, searchQuery)
    intent.putExtra(ExampleActivity.MAX_COUNT_KEY, maxCount)
    return intent
}

// With Anko-commons
fun createIntent(context: Context, searchQuery: String, maxCount: Int): Intent {
    return context.intentFor<ExampleActivity>(
        ExampleActivity.SEARCH_KEY to searchQuery,
        ExampleActivity.MAX_COUNT_KEY to maxCount
    )
}
```

##### Intent for activity with flags
```kotlin
// Without Anko-commons
fun createIntent(context: Context): Intent {
    val intent = Intent(context, ExampleActivity::class.java)
    intent.flags = Intent.FLAG_ACTIVITY_SINGLE_TOP
    return intent
}
// With Anko-commons
fun createIntent(context: Context): Intent {
    return context.intentFor<ExampleActivity>().singleTop()
}
```

##### Starting activity
```kotlin
// Without Anko-commons
fun navigateToExample(example: Example) {
    val intent = Intent(this, ExampleActivity::class.java)
    intent.putExtra(ExampleActivity.EXAMPLE_KEY, example)
    startActivity(intent)
}
// With Anko-commons
fun navigateToExample(example: Example) {
    startActivity(intentFor<ExampleActivity>(ExampleActivity.EXAMPLE_KEY to example))
    // Or just
    startActivity<ExampleActivity>(ExampleActivity.EXAMPLE_KEY to example)
    // Or for result
    startActivityForResult<ExampleActivity>(EXAMPLE_REQUEST_CODE, ExampleActivity.EXAMPLE_KEY to example)
}
```
