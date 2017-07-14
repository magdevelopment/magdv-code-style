# Using of Anko Commons Dialogs

##### Toasts
```kotlin
// Without anko-commons
fun showMessage(message: String) {
    Toast.makeText(this, message, Toast.LENGTH_SHORT).show()
    Toast.makeText(this, message, Toast.LENGTH_LONG).show()
}
// With anko-commons
fun showMessage(message: String) {
    toast(message)
    longToast(message)
}
```

##### Alerts
```kotlin
// Without anko-commons
fun showMessage() {
    AlertDialog.Builder(this)
        .setTitle("Title")
        .setMessage(R.string.message)
        .setPositiveButton("Ok") { dialog, which -> /*Do something*/ }
        .setNegativeButton("Nooo") { dialog, which -> /*Do something*/ }
        .show()
}
// With anko-commons
fun showMessage() {
    alert {
        title = "Title"
        messageResource = R.string.message
        positiveButton("Ok") { dialog -> /*Do something*/ }
        negativeButton("Nooo") { /*Do something*/ }
    }.show()
}
```

##### Single select dialog
```kotlin
// Without anko-commons
fun showSelectDialog(items: List<String>) {
    AlertDialog.Builder(this)
        .setTitle("Title")
        .setItems(items) { dialog, which -> /*Do something*/ }
        .show()
}
// With anko-commons
fun showSelectDialog(items: List<String>) {
    selector("Title", items) { dialog, which -> /*Do something*/ }
}
```
