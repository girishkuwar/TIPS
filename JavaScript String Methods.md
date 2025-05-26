javascript string methods

length

```javascript
let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
let length = text.length;
```

------

\" inserts a double quote in a string:

```javascript
let text = "We are the so-called \"Vikings\" from the north.";
```

------

## JavaScript String charAt()

The `charAt()` method returns the character at a specified index (position) in a string:

```javascript
let text = "HELLO WORLD";
let char = text.charAt(0);
```

------

## Extracting String Parts

There are 3 methods for extracting a part of a string:

## JavaScript String slice()

`slice()` extracts a part of a string and returns the extracted part in a new string.

The method takes 2 parameters: start position, and end position (end not included).
```javascript
// Slice out a portion of a string from position 7 to position 13:
let text = "Apple, Banana, Kiwi";
let part = text.slice(7, 13);
```

## JavaScript String substring()

`substring()` is similar to `slice()`.

The difference is that start and end values less than 0 are treated as 0 in `substring()`.

```javascript
let str = "Apple, Banana, Kiwi";
let part = str.substring(7, 13);
```

## JavaScript String substr()

`substr()` is similar to `slice()`.

The difference is that the second parameter specifies the **length** of the extracted part.

```javascript
let str = "Apple, Banana, Kiwi";
let part = str.substr(7, 6);
```

------

## JavaScript String concat()

`concat()` joins two or more strings:

```javascript
let text1 = "Hello";
let text2 = "World";
let text3 = text1.concat(" ", text2);
```

## JavaScript String trim()
The `trim()` method removes whitespace from both sides of a string:
```javascript
let text1 = "      Hello World!      ";
let text2 = text1.trim();
```

## JavaScript String trimStart()

[ECMAScript 2019](https://www.w3schools.com/js/js_2019.asp) added the String method `trimStart()` to JavaScript.

The `trimStart()` method works like `trim()`, but removes whitespace only from the start of a string.
```javascript
let text1 = "     Hello World!     ";
let text2 = text1.trimStart();
```

## Converting a String to an Array

## JavaScript String split()

A string can be converted to an array with the `split()` method:

```javascript
text.split(",")    // Split on commas
text.split(" ")    // Split on spaces
text.split("|")    // Split on pipe
```

______



# JavaScript String Search

## JavaScript String indexOf()

The `indexOf()` method returns the **index** (position) of the **first** occurrence of a string in a string, or it returns -1 if the string is not found:

```javascript
let text = "Please locate where 'locate' occurs!";
let index = text.indexOf("locate");
```

## JavaScript String lastIndexOf()

The `lastIndexOf()` method returns the **index** of the **last** occurrence of a specified text in a string:

```javascript
let text = "Please locate where 'locate' occurs!";
let index = text.lastIndexOf("locate");
```

## JavaScript String matchAll()

The `matchAll()` method returns an iterator containing the results of matching a string against a string (or a regular expression).

```javascript
const iterator = text.matchAll("Cats");
```

## JavaScript String includes()

The `includes()` method returns true if a string contains a specified value.

Otherwise it returns `false`.

```javascript
let text = "Hello world, welcome to the universe.";
text.includes("world");
```





















