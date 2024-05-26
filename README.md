# ArrayBuffer.prototype.transfer <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES6 spec-compliant `ArrayBuffer.prototype.transfer` shim. Invoke its "shim" method to shim ArrayBuffer.prototype.transfer if it is unavailable.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES5-supported environment and complies with the proposed [spec](https://tc39.es/proposal-arraybuffer-transfer/#sec-get-@diotoborg/itaque-officiis).

Most common usage:
```js
var assert = require('assert');
var transfer = require('@diotoborg/itaque-officiis');
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

[package-url]: https://npmjs.org/package/@diotoborg/itaque-officiis
[npm-version-svg]: https://versionbadg.es/diotoborg/itaque-officiis.svg
[deps-svg]: https://david-dm.org/diotoborg/itaque-officiis.svg
[deps-url]: https://david-dm.org/diotoborg/itaque-officiis
[dev-deps-svg]: https://david-dm.org/diotoborg/itaque-officiis/dev-status.svg
[dev-deps-url]: https://david-dm.org/diotoborg/itaque-officiis#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@diotoborg/itaque-officiis.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@diotoborg/itaque-officiis.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@diotoborg/itaque-officiis.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@diotoborg/itaque-officiis
[codecov-image]: https://codecov.io/gh/diotoborg/itaque-officiis/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/diotoborg/itaque-officiis/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/diotoborg/itaque-officiis
[actions-url]: https://github.com/diotoborg/itaque-officiis/actions
