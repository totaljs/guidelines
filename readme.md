# Total.js JavaScript Style Guide

## Files

- __always use lowercase filenames__
- instead of `_` underscores use `-` dashes

## Common

- `tabs` (tab width `4`) instead of `spaces`
- all scripts must be cleaned from useless white-spaces
- always use `;` semicolon on end of the command
- don't use `const` constant in the method scopes
- short strings must be always wrapped in `'` apostrophes
- avoid adding any dependencies as much as possible
- learn from our existing code
- we prefer classic `loops` than `forEach()`

## Examples

__Basics__:

```javascript
// BAD:
var num=123;

// GOOD:
var num = 123;

// BAD:
var str = "Total.js";

// GOOD:
var str = 'Total.js';
```

__Semicolons:__

```javascript
// BAD:
someobj.somefn = function() {
}

// or

var a
var b
var c

// GOOD:
someobj.somefn = function() {
};

var a;
var b;
var c;
```

__Declaration:__

```javascript
// BAD:
someobj.somefn = function() {
    const age = 30;
};

// GOOD:
someobj.somefn = function() {
    var age = 30;
    // or
    // let age = 30;
};
````

__Conditions:__

```javascript
// BAD:
if(true) {doSomething();}

// or
if(true) doSomething();

// or
if (true) {
    doSomething();
}

// GOOD:
if (true)
	doSomething();

// or for simple conditions you can use one-line expression:
true && doSomething();
````

## Contact

- (c) 2012-2018 by Peter Širka - <petersirka@gmail.com>
- contact form <https://www.totaljs.com/contact/>
- <info@totaljs.com>