Node.js Coding guidelines
==========================

## Tab size is 4 space
Do not indent using mixed spaces and tabs ever

## New lines
Only linux newline terminator `\n` is allow in a repository. Windows `\n\r` is forbidden

## No trailing whitespace
Do not leaving trailing whitespace at the end of files or lines of code.

## Semicolons
Using semicolons is a long time argument in the javascript community. If you don't want to use semicolons, make sure that you understand the [rules](http://inimino.org/~inimino/blog/javascript_semicolons) PERFECTLY.

## Use single quotes
Use only single quotes, unless its a .json file.

*Right*
```js
var x = 'lalala';
```

*Wrong*
```js
var x = "lalala";
```

## Opening braces go on the same line
*Right*
```js
function foo () {
}
```

*Wrong*
```js
function foo()
{
}
```
## Variables 

TBD

## Use UpperCamelCase for script files the contain a single class definition
*Right*
```
FooBar.js
```

*wrong*
```
fooBar.js
foo_bar.js
```

## Use lowerCamelCase for script files with mixed content (not the above)

## Use lowerCamelCase for variables, properties and function names

Variables, properties and function names should use `lowerCamelCase`.  They
should also be descriptive. Single character variables and uncommon
abbreviations should generally be avoided.

*Right:*
```js
var fooBar = 1;
```

*Wrong:*
```js
var foo_bar = 1;
```

## Use UpperCamelCase for class names

Class names should be capitalized using `UpperCamelCase`.

*Right:*
```js
function MyClass() {
}
```

*Wrong:*
```js
function myClass() {
}
```

*Wrong:*
```js
function my_Class() {
}
```

## Use UPPERCASE for Constants

Constants should be declared as regular variables or static class properties,
using all uppercase letters.

Node.js / V8 actually supports mozilla's [const][const] extension, but
unfortunately that cannot be applied to class members, nor is it part of any
ECMA standard.

*Right:*
```js
var SECOND = 1 * 1000;

function File() {
}
File.FULL_PERMISSIONS = 0777;
```

*Wrong:*
```js
const SECOND = 1 * 1000;

function File() {
}
File.fullPermissions = 0777;
```

[const]: https://developer.mozilla.org/en/JavaScript/Reference/Statements/const

## Object / Array creation

Use trailing commas and put *short* declarations on a single line. Only quote
keys when your interpreter complains:

*Right:*
```js
var a = ['hello', 'world'];
var b = {
  good: 'code',
  'is generally': 'pretty',
};
```

*Wrong:*

```js
var a = [
  'hello', 'world'
];
var b = {"good": 'code'
        , is generally: 'pretty'
        };
```

## Use the === operator

Almost always use the triple equality operator as it will work just as expected. Only rarely will you need ==

*Right:*
```js
var a = 0;
if (a === '') {
  console.log('winning');
}

```

*Wrong:*
```js
var a = 0;
if (a == '') {
  console.log('losing');
}
```

## Specify all require statements at the start of a file

*Right:*
```js
  var dependency = require('dependency');
  
  var x = dependency.foo();
```

*Wrong:*
```js
var a = { b: 'c' };

console.log(require('util').inspect(a));
```

*Wrong:*
```js
function x() {
}

var fs = require('fs');
```

## Module exports should be at start of a file
Preferably as close as possible to the require statements.

Some ideas and varbatim text taken from:
[felixge node style guide](https://github.com/felixge/node-style-guide/blob/master/Readme.md)
