# Total.js JavaScript Style Guide

## Filenames

- __filenames should be all lowercase__
- use `-` dashes instead of `_` underscores

## Common

- use `tabs` (tab width `4`) instead of `spaces`
- remove all unnecessary white-spaces
- always use `;` semicolon at the end of a command
- don't use `const` constant in the method scopes
- short strings should be always wrapped in `'` apostrophes
- avoid adding any dependencies as much as possible
- learn from our existing code
- use classic `loops` over `forEach()` where possible

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

// or for a simple conditions you can use inline expression:
true && doSomething();
````

## Contact

- (c) 2012-2018 by Peter Širka - <petersirka@gmail.com>
- contact form <https://www.totaljs.com/contact/>
- <info@totaljs.com>
