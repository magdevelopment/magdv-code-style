# Copyright template

1. Заходим: Settings → Editor → Copyright → Copyright Profiles.
1. Добавляем новый профиль. Имя профиля можно ассоциировать с именем разработчика.
1. В поле Regexp to detect copyright in comments оставляем Copyright если он там есть или вписываем.
1. В поле Allow replace copyright if old copyright matches вписываем свое имя и фамилию так, как они будут выглядеть в шаблоне копирайта.
1. В поле Copyright text вставляем следующий шаблон:

```
Copyright © $today.year MAG Development, LLC. All rights reserved.
Project: [project]
Date: ${today.format('dd.MM.yyyy')}
Time: ${today.format('HH:mm')}
Author: [author] <[email account] at magdv.com>
```
Где, в квадратных скобках:

* project - проект (MAG.Online, MAG.Express, Cargomart и т.д.)
* author – автор файла латинскими буквами
* email account – имя вашего аккаунта в корпоративной почте

Квадратные скобки в шаблоне не оставляем.

## Как это использовать?
В редакторе жмем **Alt+Insert** и выбираем **Copyright**.

Смысл всех махинаций в том, что при отсутствии копирайта, IDE генерирует новый в положенном месте, а в случае наличия – обновляет. Обновление происходит только если копирайт принадлежит вам, что определяется пунктом 4 данного руководства.
