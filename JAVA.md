# Java

## Introduction

Like JavaScript, Java:
* uses semi-colons at the end of statements

Unlike JavaScript, Java:
* is a compiled language
* is an object-oriented language, i.e. everything must be inside a class
* is a typed language. Say goodbye to `var`, and start getting used to `int`, `String`, and so on!


## Cheatsheet

### Strings
JavaScript | Java
---------- | ----
`str[i]` or `str.charAt(i)` | `str.charAt(i)`
`str.length` | `str.length()`
`''` or `""` | `""`*

*Single quotes in Java are used to indicate a character, which is a separate data type. Thus, if you use single quotes, you must enclose exactly one character - anything else (e.g. `''`, `'abc'`) will throw an error.

JavaScript has a nice built-in syntax of treating a string as an array of characters. To get this behavior in Java, use `str.toCharArray()` to get the string as a (new) character array. You can modify as desired, and then use `new String(charArray)` to get a string again.

Other notes:
* Java string concatenation is horrendously slow. Better to use `StringBuilder` to create larger strings.


### Arrays
JavaScript | Java
---------- | ----
`var arr = [];` | `int[] arr = new int[5];`*
`arr.length` | `arr.length`

*Or whatever data type and array length. Note that a length IS required in Java!