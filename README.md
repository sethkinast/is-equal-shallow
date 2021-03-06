# is-equal-shallow [![NPM version](https://badge.fury.io/js/is-equal-shallow.svg)](http://badge.fury.io/js/is-equal-shallow)  [![Build Status](https://travis-ci.org/jonschlinkert/is-equal-shallow.svg)](https://travis-ci.org/jonschlinkert/is-equal-shallow) 

> Does a shallow comparison of two objects, returning false if the keys or values differ.

The purpose of this lib is to do the fastest comparison possible of two objects when the values will predictably be primitives. 

- only compares objects.
- only compares the first level of each object
- values must be primitives. If a value is not a primitive, even if the values are the same, `false` is returned.

## Install with [npm](npmjs.org)

```bash
npm i is-equal-shallow --save
```


## Usage

```js
var equals = require('is-equal-shallow');
equals(object_a, object_b);
```

**Examples**

```js
equals({a: true, b: true}, {a: true, b: true});
//=> 'true'

equals({a: true, b: false}, {c: false, b: false});
//=> 'false'

equals({a: true, b: false}, {a: false, b: false});
//=> 'false'
```

Strict comparison for equality:

```js
equals({a: true, b: true}, {a: true, b: 'true'});
//=> 'false'
```

When values are not primitives, `false` is always returned:

```js
equals({ b: {}}, { b: {}});
//=> 'false'

equals({ b: []}, { b: []});
//=> 'false'
```


## Run tests

Install dev dependencies:

```bash
npm i -d && npm test
```

## Contributing
Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/jonschlinkert/is-equal-shallow/issues)

## Author

**Jon Schlinkert**
 
+ [github/jonschlinkert](https://github.com/jonschlinkert)
+ [twitter/jonschlinkert](http://twitter.com/jonschlinkert) 

## License
Copyright (c) 2015 Jon Schlinkert  
Released under the MIT license

***

_This file was generated by [verb](https://github.com/assemble/verb) on February 25, 2015._
