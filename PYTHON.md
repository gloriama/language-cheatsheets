# Python

## Introduction

Like JavaScript, Python:
* is an interpreted language
* is dynamically typed

Unlike JavaScript, Python:
* uses whitespace indentation. No more semi-colons!
* is strongly typed. If operations are attempted on values of the wrong type, it will throw an error instead of trying to coerce types.
* has gloriously simple built-in ways to convert items from one type to another, including between sets and lists.

## Cheatsheet

### Basic
JavaScript | Python
---------- | ------
`console.log('hello world')` | `print('hello world')`
`// comment` | `# comment`
`function myFunc(param) { ... }` | `def myFunc(param):`


### Classes
JavaScript (pseudoclassical style):
```
var Constructor = function() {
  ...
}
Constructor.prototype.method = function(param1, param2) {
  ...
}
```

Python:
```
class Constructor:
  def method(self, param1, param2):
    ...
```


### Control flow
JavaScript | Python
---------- | ------
`if ( ... )` | `if ...:`
`for (var i = 0; i < max; i++)` | `for i in range(max):`
`condition ? ifTrue : ifFalse` | `ifTrue if condition else ifFalse`


### Strings
JavaScript | Python
---------- | ------
`str[i]` | `str[i]`
`str.length` | `len(str)`
`str.slice(i, j)` | `str[i:j]`
`str.slice(0, j)` | `str[:j]`
`str.slice(i)` | `str[i:]`
`str.slice()` | `str[:]`
`for (var i = 0; i < str.length; i++)` | `for char in s:`
`'a'.charCodeAt(0)` | `ord('a')`
`str.split(',')` | `str.split(',')`
`str.split('')` | `list(str)`

Python also has an "extended slice" syntax, where you can specify a third item: `str[start:end:step]`, where `step` refers to how you'd like to hop through the string from `start` to `end` (default is 1). Thus, to reverse a string you can actually use the incredibly cryptic `str[::-1]`.


### Objects/Dicts
JavaScript | Python
---------- | ------
`var obj = {};` | `dict = {}`
`{ a: 1 }` | `{ 'a': 1 }`*
`obj.propertyName` or `obj['propertyName']` | `dict['propertyName']`
`obj[key]` | `dict[key]` or `dict.get(key)`**
`obj[key] || 0` | `dict.get(key, 0)`
`delete obj[key]` | `del dict[key]`***
`Object.keys(obj)` | `dict.keys()`
`key in obj` | `dict.has_key(key)`

\*Note Python can take keys of different types (string, number, `None` - though not Booleans, arrays, or other dicts). Therefore it does **not** automatically stringify keys.

\*\*Note that if you use `dict[key]` and the key does not exist, Python will throw an error. To avoid this and get more JavaScript-like behavior, use `dict.get(key)`, which fails more gracefully and returns `None` if not found.

\*\*\*Note that unlike JavaScript, Python's `del` will throw an error if the key does not exist.

In general, objects are very similar in JavaScript and Python, in both syntax and usage. In Python, they are generally called dictionaries (or dicts).

One major difference between JavaScript and Python is how they treat **equality**. Are two objects/dicts with the same values but in different memory locations considered equal? Not in JavaScript, but *yes* in Python.


### Sets
JavaScript | Python
---------- | ------
`new Set()` | `set()`
`s.add(item);` | `s.add(item)`
`s.delete(item);` | `s.remove(item)`
`s.has(item)` | `item in s`

To convert an array `arr` to a set in Python, simply use `set(arr)`.

### Arrays/Lists
JavaScript | Python
---------- | ------
`arr.length` | `len(arr)`
`arr.slice(i, j)` | `arr[i:j]`
`arr.slice(0, j)` | `arr[:j]`
`arr.slice(i)` | `arr[i:]`
`arr.slice()` | `arr[:]`
`for (var i = 0; i < arr.length; i++)` | `for item in arr:`
`arr.push(value)` | `arr.append(value)`
`arr.sort()` | `sorted(arr)`
`arr = arr.concat(newArr)` | `arr += newArr`

Arrays are very similar in JavaScript and Python, in both syntax and usage. In particular, both are variable-length (unlike languages like C and Java where arrays are fixed-length and do not contain methods such as push or pop).

Note that in Python, you cannot set the value of an array index if the array does not already contain that index. The array must already have an item at an index (e.g. via append or initialization) for it to be set to something else. Otherwise, it will throw an error.


### Math
JavaScript | Python
---------- | ------
`Math.ceil` | `math.ceil` and so on
`Math.min`, `Math.max` | `min`, `max`
`Math.pow(a, b)` | `math.pow(a, b)` or `a ** b`

Note that in JavaScript, `5/2 === 2.5` but in Python, `5/2 == 2`.


### Operators
JavaScript | Python
---------- | ------
`&&` | `and`
`||` | `or`
`!` | `not`
`===` | `==`*
`!==` | `!=`*
`!root` | `root == None`*
`i++` | `i += 1`

\*The differences above are because all values are already typed in Python, so it is never necessary to specify that items should not be coerced to the same type before testing for equality/non-equality.

Note that the concept of "truthy" and "falsy" values no longer exist in Python - either a value is a Boolean or not. So expressions like `if (!root) { ... }`, which are ubiquitous in JavaScript, do not work in Python. Instead, an explicit check of `root == None` (or `x == 0`, or so on) must be used.


### Booleans
JavaScript | Python
---------- | ------
`true` | `True`
`false` | `False`


### Null/Undefined
JavaScript | Python
---------- | ------
`null` | `None`

There is no equivalent to `undefined` in Python.


### Higher-Order Functions
JavaScript | Python
---------- | ------
`arr.reduce(func)` | `reduce(func, arr)`
`arr.map(function(x) { return x*x; })` | `[ x*x for x in arr]`