Это изменённая копия [Markdown Here](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)  
Здесь описаны все возможности, поддерживаемые внутриигровым просмотрщиком вики CPM. 

Это краткий справочник с примерами. Более подробные сведения доступны в [исходной спецификации Джона Грубера](http://daringfireball.net/projects/markdown/) и на [странице о Github-flavored Markdown](http://github.github.com/github-flavored-markdown/).


<a name="table-of-contents"/>

##### Содержание  
[Заголовки](#headers)  
[Выделение](#emphasis)  
[Списки](#lists)  
[Ссылки](#links)  
[Изображения](#images)  
[Код и подсветка синтаксиса](#code)  
[Сноски](#footnotes)  
[Таблицы](#tables)  
[Цитаты](#blockquotes)  
[Горизонтальная линия](#hr)  
[Переносы строк](#lines)  
[Видео YouTube](#videos)  
[Выделенные сообщения и предупреждения](#highlighting)  

<a name="headers"/>

## Заголовки

```no-highlight
<a name="custom-name"/>


<a name="h1"/>

# H1

<a name="h2"/>

## H2

<a name="h3"/>

### H3

<a name="h4"/>

#### H4

<a name="h5"/>

##### H5

<a name="h6"/>

###### H6

[Jump To H1](#custom-name)
```

<a name="custom-name"/>


<a name="h1"/>

# H1

<a name="h2"/>

## H2

<a name="h3"/>

### H3

<a name="h4"/>

#### H4

<a name="h5"/>

##### H5

<a name="h6"/>

###### H6

[Перейти к H1](#custom-name)

<a name="emphasis"/>

## Выделение

```no-highlight
Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~
```

Выделение курсивом с помощью *звёздочек* или _подчёркиваний_.

Сильное выделение, то есть полужирный шрифт, с помощью **звёздочек** или __подчёркиваний__.

Комбинированное выделение с помощью **звёздочек и _подчёркиваний_**.

Для зачёркивания используются две тильды. ~~Зачеркнуть это.~~


<a name="lists"/>

## Списки

(В этом примере начальные и конечные пробелы показаны точками: ⋅)

```no-highlight
1. First ordered list item
2. Another item
⋅⋅* Unordered sub-list. 
1. Actual numbers matter, this is different from the spec.
⋅⋅1. Ordered sub-list
4. And another item.

⋅⋅⋅You can have properly indented paragraphs within list items. Notice the blank line above, and the leading spaces (at least one, but we'll use three here to also align the raw Markdown).

⋅⋅⋅To have a line break without a paragraph, you will need to use two trailing spaces.⋅⋅
⋅⋅⋅Note that this line is separate, but within the same paragraph.⋅⋅
⋅⋅⋅(This is contrary to the typical GFM line break behaviour, where trailing spaces are not required.)

* Unordered list can use asterisks
- Or minuses
+ Or pluses
```

1. Первый пункт нумерованного списка
2. Ещё один пункт
  * Вложенный маркированный список. 
1. Фактические номера имеют значение; это отличается от спецификации.
  1. Вложенный нумерованный список
4. И ещё один пункт.

   Внутри пунктов списка можно размещать абзацы с правильными отступами. Обратите внимание на пустую строку выше и начальные пробелы (нужен хотя бы один, но здесь используются три, чтобы выровнять и исходный Markdown).

   Для переноса строки без нового абзаца нужны два пробела в конце строки.  
   Эта строка отображается отдельно, но остаётся в том же абзаце.  
   (Это отличается от обычного поведения переносов строк в GFM, где пробелы в конце не требуются.)

* В маркированном списке можно использовать звёздочки
- Или минусы
+ Или плюсы

<a name="links"/>

## Ссылки

Есть два способа создания ссылок.

```no-highlight
[I'm an inline-style link](https://www.google.com)

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

[I'm a reference-style link][Arbitrary case-insensitive reference text]

[I'm a relative reference to a repository file](../blob/master/LICENSE)

[You can use numbers for reference-style link definitions][1]

[The text itself] won't work.

Some text to show that the reference links can follow later.

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[1]: http://slashdot.org
```

[Это встроенная ссылка](https://www.google.com)

[Это встроенная ссылка с заголовком](https://www.google.com "Главная страница Google")

[Это ссылка по идентификатору][Arbitrary case-insensitive reference text]

[Это относительная ссылка на файл репозитория](../blob/master/LICENSE)

[В определениях ссылок по идентификатору можно использовать числа][1]

[Сам текст] не сработает.

Этот текст показывает, что определения ссылок могут находиться ниже.

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[1]: http://slashdot.org

<a name="images"/>

## Изображения

Все изображения нужно загрузить в репозиторий вики.  
Поместите изображения в `Localization/wiki/images`; по возможности используйте уже существующие изображения.  

```no-highlight
Here's a spinner (hover to see the title text):

Inline-style: 
![alt text](https://github.com/tom5454/CustomPlayerModels/wiki/images/spinner.png "Spinner Text 1")

Reference-style: 
![alt text][logo]

[logo]: https://github.com/tom5454/CustomPlayerModels/wiki/images/spinner.png "Spinner Text 2"
```

Вот поле изменения числа (наведите курсор, чтобы увидеть заголовок):

Встроенный вариант: 
![Альтернативный текст](https://github.com/tom5454/CustomPlayerModels/wiki/images/spinner.png "Текст поля изменения числа 1")

Вариант по идентификатору: 
![Альтернативный текст][logo]

[logo]: https://github.com/tom5454/CustomPlayerModels/wiki/images/spinner.png "Текст поля изменения числа 2"

<a name="code"/>

## Код и подсветка синтаксиса

Блоки кода входят в спецификацию Markdown, а подсветка синтаксиса — нет. Однако многие средства отображения, в том числе GitHub, поддерживают её. Поддерживаемые языки и написание их названий зависят от средства отображения.

```no-highlight
Inline `code` has `back-ticks around` it.
```

Встроенный `code` окружён `back-ticks around`.

Блоки кода ограничиваются строками с тремя обратными кавычками '\`\`\`'.

```
\```java
public static void test() {
	String s = "Java syntax highlighting, only on GitHub";
	System.out.println(s);
}
\```
 
\```
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
\```
```


```java
public static void test() {
	String s = "Java syntax highlighting";
	System.out.println(s);
}
```

```
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
```


<a name="footnotes"/>

## Сноски

Сноски не входят в основную спецификацию Markdown, но [поддерживаются GFM](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#footnotes).

```no-highlight
Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].  

You can also use words, to fit your writing style more closely[^note].

[^1]: My reference.
[^2]: Every new line should be prefixed with 2 spaces.  
  This allows you to have a footnote with multiple lines.
[^note]:
    Named footnotes will still render with numbers instead of the text but allow easier identification and linking.  
    This footnote also has been made with a different syntax using 4 spaces for new lines.
```

Вот простая сноска[^1].

Сноска также может занимать несколько строк[^2].  

Можно использовать слова, чтобы лучше соответствовать стилю текста[^note].

[^1]: Моя ссылка.
[^2]: Каждая новая строка должна начинаться с 2 пробелов.  
  Это позволяет создавать многострочные сноски.
[^note]:
    Именованные сноски всё равно отображаются с номерами вместо текста, но упрощают поиск и создание ссылок.  
    Эта сноска также использует другой синтаксис: 4 пробела перед новыми строками.

<a name="tables"/>

## Таблицы

Таблицы не входят в основную спецификацию Markdown, но входят в GFM и поддерживаются просмотрщиком вики CPM. Это простой способ добавить таблицы на страницу вики.

```no-highlight
Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are required, and you don't need to make the 
raw Markdown line up prettily. You can also use inline Markdown.

| Markdown | Less | Pretty |
| --- | --- | ---
| *Still* | `renders` | **nicely** |
| 1 | 2 | 3 |
```

Двоеточия позволяют выравнивать столбцы.

| Таблицы       | Это           | Здорово |
| ------------- |:-------------:| -----:|
| столбец 3     | по правому краю | $1600 |
| столбец 2     | по центру     |   $12 |
| чередование полос | удобно    |    $1 |

Ячейки заголовка должны отделяться хотя бы 3 дефисами. Внешние вертикальные черты (|) обязательны; красиво выравнивать исходный Markdown не нужно. Можно использовать и встроенную разметку Markdown.

| Markdown | Менее | Красиво |
| --- | --- | --- |
| *Всё равно* | `renders` | **хорошо** |
| 1 | 2 | 3 |

<a name="blockquotes"/>

## Цитаты

```no-highlight
> Blockquotes are very handy
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote. 
```

> Цитаты очень удобны
> Эта строка — часть той же цитаты.

Разрыв цитаты.

> Это очень длинная строка, которая останется частью цитаты даже после переноса. Продолжим писать, чтобы строка оказалась достаточно длинной для переноса на любом экране. В цитату можно *добавлять* **Markdown**. 

<a name="hr"/>

## Горизонтальная линия

```
Three or more...

---

Hyphens

***

Asterisks

___

Underscores
```

Три или больше...

---

Дефисы

***

Звёздочки

___

Подчёркивания

<a name="lines"/>

## Переносы строк

Чтобы понять работу переносов строк, лучше экспериментировать: нажмите &lt;Enter&gt; один раз (добавьте один перевод строки), затем дважды (добавьте два перевода строки) и посмотрите на результат. Вы быстро научитесь получать нужный вид. Функция «Markdown Toggle» в этом поможет. 

Вот несколько примеров для проверки:

```
Here's a line for us to start with.

This line is separated from the one above by two newlines, so it will be a *separate paragraph*.

This line is also a separate paragraph, but...
This line is only separated by a single newline, so it's a separate line in the *same paragraph*.
```

Начнём с этой строки.

Эта строка отделена от предыдущей двумя переводами строки, поэтому образует *отдельный абзац*.

Эта строка тоже начинает отдельный абзац, но...  
Эта строка отделена только одним переводом строки, поэтому отображается отдельно в *том же абзаце*.

<a name="videos"/>

## Видео YouTube

Видео нельзя вставить напрямую, но можно добавить изображение со ссылкой на видео:

```no-highlight
[![IMAGE ALT TEXT HERE](https://github.com/tom5454/CustomPlayerModels/wiki/images/spinner.png)](http://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)
```

[![АЛЬТЕРНАТИВНЫЙ ТЕКСТ ИЗОБРАЖЕНИЯ](https://github.com/tom5454/CustomPlayerModels/wiki/images/spinner.png)](http://www.youtube.com/watch?v=dQw4w9WgXcQ)

О загрузке собственного изображения см. раздел [Изображения](#images).

<a name="highlighting"/>

## Выделенные сообщения / предупреждения

Раздел взят из [документации GitHub](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#alerts)

```
> [!NOTE]
> Useful information that users should know, even when skimming content.

> [!TIP]
> Helpful advice for doing things better or more easily.

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.
```

> [!NOTE]
> Полезная информация, которую стоит знать даже при беглом чтении.

> [!TIP]
> Советы, помогающие выполнять действия лучше или проще.

> [!IMPORTANT]
> Ключевая информация, необходимая для достижения цели.

> [!WARNING]
> Срочная информация, требующая немедленного внимания во избежание проблем.

> [!CAUTION]
> Предупреждение о рисках или негативных последствиях определённых действий.

---

Лицензия источника: [CC-BY](https://creativecommons.org/licenses/by/3.0/)
