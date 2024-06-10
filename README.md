# ArrayBuffer.prototype.transfer <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES6 spec-compliant `ArrayBuffer.prototype.transfer` shim. Invoke its "shim" method to shim ArrayBuffer.prototype.transfer if it is unavailable.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES5-supported environment and complies with the proposed [spec](https://tc39.es/proposal-arraybuffer-transfer/#sec-get-@hishprorg/velit-nesciunt-esse).

Most common usage:
```js
var assert = require('assert');
var transfer = require('@hishprorg/velit-nesciunt-esse');
var IsDetachedBuffer = require('es-abstract/2023/IsDetachedBuffer');

var ab = new ArrayBuffer('a');

assert.equal(IsDetachedBuffer(ab), false);
transfer(ab);
assert.equal(IsDetachedBuffer(ab), true);

if (!ArrayBuffer.prototype.transfer) {
	transfer.shim();
}

var ab2 = new ArrayBuffer('a');
assert.equal(IsDetachedBuffer(ab2), false);
ab2.transfer();
assert.equal(IsDetachedBuffer(ab2), true);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@hishprorg/velit-nesciunt-esse
[npm-version-svg]: https://versionbadg.es/hishprorg/velit-nesciunt-esse.svg
[deps-svg]: https://david-dm.org/hishprorg/velit-nesciunt-esse.svg
[deps-url]: https://david-dm.org/hishprorg/velit-nesciunt-esse
[dev-deps-svg]: https://david-dm.org/hishprorg/velit-nesciunt-esse/dev-status.svg
[dev-deps-url]: https://david-dm.org/hishprorg/velit-nesciunt-esse#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@hishprorg/velit-nesciunt-esse.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@hishprorg/velit-nesciunt-esse.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@hishprorg/velit-nesciunt-esse.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@hishprorg/velit-nesciunt-esse
[codecov-image]: https://codecov.io/gh/hishprorg/velit-nesciunt-esse/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/hishprorg/velit-nesciunt-esse/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/hishprorg/velit-nesciunt-esse
[actions-url]: https://github.com/hishprorg/velit-nesciunt-esse/actions
