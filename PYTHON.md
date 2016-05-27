# Python

## Introduction

Like JavaScript, Python:
* is an interpreted language
* is dynamically typed

Unlike JavaScript, Python:
* uses whitespace indentation. No more semi-colons!
* is strongly typed. If operations are attempted on values of the wrong type, it will throw an error instead of trying to coerce types.

## Cheatsheet

### Basic
JavaScript | Python
---------- | ------
`console.log('hello world')` | `print('hello world')`
`// comment` | `# comment`


### Control flow
JavaScript | Python
---------- | ------
`if ( ... )` | `if ...:`
`for (var i = 0; i < max; i++)` | `for i in range(max):`


### Strings
JavaScript | Python
---------- | ------
`str.slice(i, j)` | `str[i:j]`
`str.slice(0, j)` | `str[:j]`
`str.slice(i)` | `str[i:]`
`str.slice()` | `str[:]`

Python also has an "extended slice" syntax, where you can specify a third item: `str[start:end:step]`, where `step` refers to how you'd like to hop through the string from `start` to `end` (default is 1). Thus, to reverse a string you can actually use the incredibly cryptic `str[::-1]`.


### Arrays
JavaScript | Python
---------- | ------
`arr.slice(i, j)` | `arr[i:j]`
`arr.slice(0, j)` | `arr[:j]`
`arr.slice(i)` | `arr[i:]`
`arr.slice()` | `arr[:]`
`for (var i = 0; i < arr.length; i++)` | `for item in arr:`


### Math
JavaScript | Python
---------- | ------
`Math.ceil` | `math.ceil` and so on
`Math.min`, `Math.max` | `min`, `max`