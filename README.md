#arabicString

A Javascript library that extends the native `String` object with methods to help when dealing with Arabic strings for _node_ and _the browser_.

##Usage
###node
```js
require('arabicString')
```
###browser
```js
<script src="arabicString.js"></script>
```

##String#howArabic()

The percentage of Arabic letters in the `String`.

### Example

```js
'foobar'.howArabic()
//=> 0.0
'فوو bar'.howArabic()
//=> 0.5
'فوبار'.howArabic()
//=> 1.0
```

##String#howNotArabic()

The precentage of non-Arabic letters in the `String`.

### Example

```js
'فوبار'.howNotArabic()
//=> 0.0
'فوو bar'.howNotArabic()
//=> 0.5
'foobar'.howNotArabic()
//=> 1.0
```

##String#isArabic(threshold)

Is the `String` Arabic, based on a given `threshold` between `0` and `1`. Defaults to `0.79`.

### Example

```js
'فوو'.isArabic()
//=> true
'فوو bar baz'.isArabic(0.5)
//=> flase
```

##String#hasArabic()

Does the `String` have _any_ Arabic letter.

### Example

```js
'فوو bar'.hasArabic()
//=> ture
'foo bar'.hasArabic()
//=> false
```

##String#removeTashkel()

Will return the `String` without the diacritics

### Example

```js
'مٌحمْد'.removeTashkel()
//=> 'محمد'
'وَتُرى الْكَوَاكِبِ فِي الْمَجَرَّةِ شَرَعَا*** مِثْلُ الظِّباءِ كوارعا فِي جَدْوَلِ'.removeTashkel()
//=> 'وترى الكواكب في المجرة شرعا *** مثل الظباء كوارعا في جدول'
```

##String#removeNonArabic()

Will return the `String` without the Arabic letters

### Example

```js
'hello مرحبا'.removeNonArabic()
//=> 'مرحبا'
```

##String#removeArabic()

Will return the `String` without the non-Arabic letters

### Example

```js
'hello مرحبا'.removeArabic()
//=> 'hello'
```

## License 

MIT

Copyright &copy; 2012 - [Ahmad Salman](https://github.com/ahmads "Ahmad Salman")
