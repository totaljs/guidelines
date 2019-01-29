# Total.js Guide

## JavaScript Style

### Filenames

- __filenames should be all lowercase__
- use `-` dashes instead of `_` underscores for filenames 

### Common

- use `tabs` (tab width `4`) instead of `spaces`
- remove all unnecessary white-spaces
- always use `;` semicolon at the end of a command
- don't use `const` constant in the method scopes
- short strings should be always wrapped in `'` apostrophes
- avoid adding any dependencies as much as possible
- learn from our existing code
- use classic `loops` over `forEach()` where possible

### Examples

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

## CSS / Styles

- __filenames should be all lowercase__
- for filenames use `-` dashes instead of `_` underscores for filenames
- __keep styles__ in the same line
- don't use vendor prefixes, but use `/*auto*/` comment for Total.js auto-prefixing
- instead of quotes use `'` apostrophes
- don't use LESS or SASS because Total.js supports variables and nested selector too

```css
/*auto*/

.class { key1: value; key2: value; key3: value; }
.class > div { key1: value; key2: value; }
```


## Contact

- (c) 2012-2018 by Peter Širka - <petersirka@gmail.com>
- contact form <https://www.totaljs.com/contact/>
- <info@totaljs.com>
