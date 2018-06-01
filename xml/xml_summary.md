# XML Code Style Summary

## Содержание
* [Именование идентификаторов элементов разметки](#Именование-идентификаторов-элементов-разметки)
* [Именование идентификаторов ресурсов цвета](#Именование-идентификаторов-ресурсов-цвета)

## Именование идентификаторов элементов разметки

Руководствуясь общим согласием переходить на `Kotlin` и использовать расширение `Kotlin Android Extensions`, решили именовать идентификаторы  (`View`, `Layout`) в **camelCase** стиле. Так же идентификатор должен содержать информацию о классе элемента.
```XML
<!-- Вот так правильно -->
<TextView
    android:id="@+id/friendNameTextView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"/>

<!-- А вот так неправильно -->
<TextView
    android:id="@+id/friend_name"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"/>

<!-- И так тоже неправильно -->
<TextView
    android:id="@+id/friendName"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"/>
```

## Именование идентификаторов ресурсов цвета
Идентификаторы ресурсов цвета должны быть названы в **camelCase** стиле. Если у цвета задан параметр `alpha`, то после цвета пишется значение `alpha` в процентах.
```XML
<!-- Вот так правильно -->
<color name="black">#000000</color>
<color name="black50">#7F000000</color>
<color name="deepPurple">#673AB7</color>

<!-- А вот так неправильно -->
<color name="black">#7F000000</color>
<color name="black_50">#7F000000</color>
<color name="black_7F">#7F000000</color>
<color name="deep_purple">#673AB7</color>
```
