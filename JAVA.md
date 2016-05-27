# Java

## Introduction

Like JavaScript, Java:
* uses semi-colons at the end of statements

Unlike JavaScript, Java:
* is a compiled language
* is an object-oriented language, i.e. everything must be inside a class
* is a typed language. Say goodbye to `var`, and start getting used to `int`, `String`, and so on!
* scopes variables to the enclosing block (including ifs, loops, functions, etc.), not only to the enclosing function. This includes variables inside a loop signature, e.g. `for (var i = 0; ... )`.


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
`var arr = [1, 2];` | `int[] arr = {1, 2};`
`[1, 2]` | `new int[] {1, 2}`
`arr.length` | `arr.length`
`for (var i = 0; i < arr.length; i++) { ... }` | `for (int item : arr) { ... }`

*Or whatever data type and array length. Note that a length IS required in Java, because Java arrays are fixed-length. If you want something more like the variable-length arrays you are used to from JavaScript, check out [Lists](#lists) below!

Note that when an `int` array is initialized in Java, each entry will be initialized to 0. In JavaScript, each item is initialized to undefined.


### Lists
JavaScript | Java
---------- | ----
`var arr = [];` | `List<Integer> list = new ArrayList<>();`
`arr.length` | `list.size()`
`arr[i]` | `list.get(i)`
`arr[i] = value;` | `list.set(i, value);`
`arr.push(value);` | `list.add(value);`
`arr.splice(i, 0, value);` | `list.add(i, value);`
`arr = arr.concat(otherArr);` | `list.addAll(otherList);`
`arr.slice(i, j)` | `list.subList(i, j)`

Lists are linked lists, and are best used in place of JavaScript arrays that are expected to change their length, e.g. via push, pop, etc. Syntactically (and of course nominally), JavaScript arrays look like Java arrays, but in many usages are actually more like Java lists.


### Objects/Sets
JavaScript | Java
---------- | ----
`var obj = {};` | `Map<String, Integer> map = new HashMap<>();`*
`var set = new Set();` | `Set<String> set = new HashSet<>();`**
`for (var item in obj) { ... }` | `for (Integer item : map.keySet()) { ... }`
`obj[key]` | `map.get(key)`
`obj[key] || 0` | `map.getOrDefault(key, 0)`
`obj[key] = value;` | `map.put(key, value);`
`Object.keys(obj)` | `map.keySet()`

\*Note that the pair of types between the angle brackets refers to the type for the keys and values, respectively.

\*\*Note that the type between the angle brackets refers to the type for the items in the set.


### Math

Math largely has the exact same syntax and naming:
* `Math.pow`, `Math.sqrt`
* `Math.log`
* `Math.ceil`, `Math.floor`, `Math.round`
* `Math.max`, `Math.min`

However, note that in Java, these all return values of type double (even `ceil`, `floor`, and `round`). So if you want to compare these to values of type int, you must cast them to integers prefixing the expressions with `(int)`. Note that casting truncates the values, therefore rounding down automatically.


### Operators
JavaScript | Java
---------- | ----
`===` | `==`
`!==` | `!=`
`!root` | `root == null`*

As in most languages, the operators (mathematical, bitwise, logical) are all largely the same. The differences above are because all values are already typed in Java, so it is never necessary to specify that items should not be coerced to the same type before testing for equality/non-equality.

*Note that the concept of "truthy" and "falsy" values no longer exist in Java - either a value is a Boolean or not. So expressions like `if (!root) { ... }`, which are ubiquitous in JavaScript, do not work in Java. Instead, an explicit check of `root == null` (or `x == 0`, or so on) must be used.