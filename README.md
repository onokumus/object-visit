# object-visit [![NPM version](https://badge.fury.io/js/object-visit.svg)](http://badge.fury.io/js/object-visit)  [![Build Status](https://travis-ci.org/jonschlinkert/object-visit.svg)](https://travis-ci.org/jonschlinkert/object-visit)

> Call the given method on each value in the given object.

## Install

Install with [npm](https://www.npmjs.com/)

```sh
$ npm i object-visit --save
```

## Usage

```js
var visit = require('object-visit');

var ctx = {
  data: {},
  set: function (key, value) {
    if (typeof key === 'object') {
      visit(ctx, 'set', key);
    } else {
      ctx.data[key] = value;
    }
  }
};

ctx.set('a', 'a');
ctx.set('b', 'b');
ctx.set('c', 'c');
ctx.set({d: {e: 'f'}});

console.log(ctx.data);
//=> {a: 'a', b: 'b', c: 'c', d: { e: 'f' }};
```

## Related projects

* [base-methods](https://www.npmjs.com/package/base-methods): Starter for creating a node.js application with a handful of common methods, like `set`, `get`,… [more](https://www.npmjs.com/package/base-methods) | [homepage](https://github.com/jonschlinkert/base-methods)
* [collection-visit](https://www.npmjs.com/package/collection-visit): Visit a method over the items in an object, or map visit over the objects… [more](https://www.npmjs.com/package/collection-visit) | [homepage](https://github.com/jonschlinkert/collection-visit)
* [map-visit](https://www.npmjs.com/package/map-visit): Map `visit` over an array of objects. | [homepage](https://github.com/jonschlinkert/map-visit)

## Running tests

Install dev dependencies:

```sh
$ npm i -d && npm test
```

## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/jonschlinkert/object-visit/issues/new).

## Author

**Jon Schlinkert**

+ [github/jonschlinkert](https://github.com/jonschlinkert)
+ [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

## License

Copyright © 2015 Jon Schlinkert
Released under the MIT license.

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on October 10, 2015._