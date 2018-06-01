# Пример форматирования XML файлов

### IDE Setup
#### Tabs and Indents
* default

#### Other
* Spaces
 * In empty tag = `true`

#### Arrangement
* default

#### Android
* AndroidManifest.xml
  * Wrap arrtibutes = `Wrap always`
  * Insert line break before first attribute = `true`
    * Include namespace declarations = `true`
* Layout Files
  * Wrap arrtibutes = `Wrap always`
  * Insert line break before first attribute = `true`
    * Include namespace declarations = `true`

### Полный пример
```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.v7.widget.CardView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="8dp"
    android:background="?attr/selectableItemBackground"
    app:cardBackgroundColor="@color/colorAccent"
    app:cardCornerRadius="4dp"
    app:cardElevation="4dp">

    <FrameLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <TextView
            android:id="@+id/idTextView"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:padding="16dp"
            android:textColor="#FFFFFF"
            android:textSize="14dp"
            tools:text="ID" />

        <ProgressBar
            android:id="@+id/progressBar"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:visibility="gone"
            tools:visibility="visible" />

    </FrameLayout>
</android.support.v7.widget.CardView>
```

### Объявление XML
Указывается на первой строке файла. Перед **корневым элементом** нет пустых строк.
```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.v7.widget.CardView
...
```

### Тэг
Открывающая скобка **тэга** расположена на одной строке с именем **тега**. Закрывающая скобка расположена на той же строке либо в на строке последнего **атрибута**.
```xml
<android.support.v7.widget.CardView>

  <TextView
      android:layout_width="match_parent"
      android:layout_height="match_parent" />

</android.support.v7.widget.CardView>
```

### Атрибуты
**Атрибуты** всегда располагаются по одному на строку и располагаются на следующей строке после открывающего **тэга**.
```xml
<android.support.v7.widget.CardView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    ...
```

### Элементы
После открывающего **тэга** и первого **элемента** всегда есть пустая строка. Между **элементами** всегда есть пустая строка. Перед закрывающим **тэгом** после **элемента** всегда есть пустая строка.

```xml
<FrameLayout
    ...>

    <TextView
        ... />

    <ProgressBar
        ... />

</FrameLayout>
```

### Закрывающий тэг
Если внутри **элемента** нет других **элементов**, то закрывающий **тег** опускается.
```xml
<FrameLayout>

    <TextView />

</FrameLayout>
```
Несколько подряд идущих закрывающих **тэгов** не разделяются пустыми строками.
```xml
<android.support.v7.widget.CardView>

    <FrameLayout>

        <TextView />

        <ProgressBar />

    </FrameLayout>
</android.support.v7.widget.CardView>
```

### Android
Если какой-то из основных аргументов (например текст у TextView) не имеет начального значения и будет задан в ходе работы приложения, то такой параметр необходимо указать через `tools`, чтобы его было видно на превью.
```xml
<TextView
    android:id="@+id/idTextView"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:text="ID" />
```
Если какой-то из элементов поумолчанию имеет аргумент `android:visibility = gone` (или `invisible`), то такому элементу так же через 'tools' проставляется аргумент `visible`, чтобы его было видно на превью.
```xml
<ProgressBar
    android:id="@+id/progressBar"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:visibility="gone"
    tools:visibility="visible" />
```
