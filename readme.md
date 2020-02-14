# Total.js Guidelines

__Topics__:

- [JavaScript Style](#javascript-style)
- [CSS / Styles](#css--styles)
- [Total.js Schemas](#totaljs-schemas)
- [UI components / jComponent](#ui-components--jcomponent)
- [SQL scripts in Total.js](#sql-scripts-in-totaljs)

## JavaScript Style

### Filenames

- __filenames should be all lowercase__
- use `-` dashes instead of `_` underscores for filenames

### Common

- use `tabs` (tab width `4`) instead of `spaces`
- remove all unnecessary white-spaces
- always use `;` semicolon at the end of the command
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

## Total.js Schemas

- schema names must be in plural
- first char in uppercase

```js
// BAD:
NEWSCHEMA('user', function(schema) {

    schema.define('name', 'Capitalize2(40)', true);

});

// GOOD:
NEWSCHEMA('Users', function(schema) {

    schema.define('name', 'Capitalize2(40)', true);

});
```

## UI components / jComponent

- keep all names in Plugins/Components/FUNC./MAIN./REPO. in __lowercase__
- keep all variables in __lowercase__
- do not create complicated objects with a lot of objects in depth (keep max. 2-3 of keys in depth)
- __think reusable__

```javascript
// =======================================
// PLUGINS
// =======================================

// BAD:
PLUGIN('Name', function(plugin) {
    plugin.doSomething = function() {
    };
});

// GOOD:
PLUGIN('name', function(exports) {
    // keep "exports." name and keep all names in lowercase
    exports.dosomething = function() {
    };
});

// =======================================
// COMPONENTS
// =======================================

// BAD:
COMPONENT('Name', function(com, settings) {

});

// GOOD:
COMPONENT('name', function(self, config, cls) {
    // keep names: "self.", "config" and "cls"
});
````

## SQL scripts in Total.js

- __table names / field names should be all lowercase__
- use `tabs` (tab width `4`) instead of `spaces`
- remove all unnecessary white-spaces
- always use `;` semicolon at the end of a SQL command
- remove all unnecessary type-casting `name<>'something'::text` to `name<>'something'`
- format SQL scripts
- divided scripts TABLES, VIEWS, STORED PROCEDURES/FUNCTIONS, INDEXES
- table names starts with `tbl_` in singular --> `tbl_user`, `tbl_product`
- tables with codelists must start with `cl_` in singular --> `cl_type`, `cl_product`
- view names starts with `view_` in singular --> `view_user`
- stored procedures starts with `sp_` in singular --> `sp_user`, etc..
- functions starts with `fn_` in singular --> `fn_user`, etc..

__Fields creating__:

- dates starts with `dt` --> `dtcreated`, `dtupdated`, `dtpaid`, etc..
- booleans must starts with `is` --> `ispaid`, `isremoved`, `ispublished`, etc.. with few exceptions
- identificators `id` (primary key), `userid` (foreign key), `productid` (foreign key), etc..
- Total.js identificators: Total.js UID = `VARCHAR(25)`, OpenPlatformID = `VARCHAR(30)`
- keep same names in different tables for example: `name`, `body`, etc..
- keep short names
- keep the sort of fields below:

```sql
-- BAD:
CREATE TABLE "public"."tbl_channel_message" (
    "channelid" varchar(25),
    "body" text,
    "id" varchar(25) NOT NULL,
    "ispinned" bool DEFAULT FALSE,
    "isrobot" bool DEFAULT FALSE,
    "userid" varchar(25),
    "countupdate" INT2 DEFAULT 0,
    "dtupdated" timestamp,
    "openplatformid" varchar(30),
    "dtcreated" timestamp DEFAULT now(),
    "ismobile" bool DEFAULT FALSE,
    "isremoved" bool DEFAULT FALSE,
    PRIMARY KEY ("id")
);

-- GOOD:
CREATE TABLE "public"."tbl_channel_message" (

    -- IDENTIFICATORS FIRST
    "id" varchar(25) NOT NULL,
    "userid" varchar(25),
    "channelid" varchar(25),
    "openplatformid" varchar(30),

    -- MAIN FIELDS
    "body" text,

    -- NUMBERS
    "countupdate" INT2 DEFAULT 0,

    -- BOOLEANS
    "ismobile" bool DEFAULT FALSE,
    "ispinned" bool DEFAULT FALSE,
    "isremoved" bool DEFAULT FALSE,
    "isrobot" bool DEFAULT FALSE,

    -- AND LAST DATES
    "dtupdated" timestamp,
    "dtcreated" timestamp DEFAULT NOW(),

    -- DO NOT FORGET FOR FOREIGN KEYS
    CONSTRAINT ...
    CONSTRAINT ...

    PRIMARY KEY ("id")
);
```

## Contact

- Use [Total.js Code Editor](https://www.totaljs.com/code/) for development
- (c) 2012-2020 by Peter Širka - <petersirka@gmail.com>
- Contact us via <https://www.totaljs.com/contact/>
- <info@totaljs.com>
