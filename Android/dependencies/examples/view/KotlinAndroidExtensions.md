# Kotlin Android Extensions Plugin

https://kotlinlang.org/docs/tutorials/android-plugin.html [Docs]

**Example Layout**
```XML
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <TextView
        android:id="@+id/sampleTextView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/sampleButton"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

</LinearLayout>
```

**Without plugin, but with [KotterKnife](https://github.com/JakeWharton/kotterknife)**
```kotlin
class SampleActivity : AppCompatActivity() {

    val sampleTextView: TextView by bindView(R.id.sampleTextView)
    val sampleButton: Button by bindView(R.id.sampleButton)

    override fun onCreate(savedInstanceState: Bundle?, persistentState: PersistableBundle?) {
        super.onCreate(savedInstanceState, persistentState)
        setContentView(R.layout.activity_sample)
        initViews()
    }

    private fun initViews() {
        sampleButton.setOnClickListener {
            sampleTextView.text = "Hello"
        }
    }
}
```

**With plugin**
```Kotlin
import kotlinx.android.synthetic.main.activity_sample.*

class SampleActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?, persistentState: PersistableBundle?) {
        super.onCreate(savedInstanceState, persistentState)
        setContentView(R.layout.activity_sample)
        initViews()
    }

    private fun initViews() {
        sampleButton.setOnClickListener {
            sampleTextView.text = "Hello"
        }
    }
}
```
