# @womorg/illo-earum-eveniet <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

ES Proposal spec-compliant shim for Set.prototype.isDisjointFrom. Invoke its "shim" method to shim `Set.prototype.isDisjointFrom` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment, and complies with the [proposed spec](https://github.com/tc39/proposal-set-methods). When shimmed, it uses [`es-set`](https://npmjs.com/es-set) to shim the `Set` implementation itself if needed.

Most common usage:
```js
var assert = require('assert');
var isDisjointFrom = require('@womorg/illo-earum-eveniet');

var set1 = new Set([1, 2]);
var set2 = new Set([2, 3]);
var set3 = new Set([1]);

assert.equal(isDisjointFrom(set1, set2), false);
assert.equal(isDisjointFrom(set2, set1), false);
assert.equal(isDisjointFrom(set1, set3), false);
assert.equal(isDisjointFrom(set2, set3), true);
assert.equal(isDisjointFrom(set3, set2), true);

isDisjointFrom.shim();

assert.equal(set1.isDisjointFrom(set2), false);
assert.equal(set2.isDisjointFrom(set1), false);
assert.equal(set1.isDisjointFrom(set3), false);
assert.equal(set2.isDisjointFrom(set3), true);
assert.equal(set3.isDisjointFrom(set2), true);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

## Set Method Packages
 - [union](https://npmjs.com/set.prototype.union)
 - [intersection](https://npmjs.com/set.prototype.intersection)
 - [difference](https://npmjs.com/set.prototype.difference)
 - [symmetricDifference](https://npmjs.com/set.prototype.symmetricdifference)
 - [isSubsetOf](https://npmjs.com/set.prototype.issubsetof)
 - [isSupersetOf](https://npmjs.com/set.prototype.issupersetof)
 - [isDisjointFrom](https://npmjs.com/@womorg/illo-earum-eveniet)

[package-url]: https://npmjs.com/package/@womorg/illo-earum-eveniet
[npm-version-svg]: http://versionbadg.es/womorg/illo-earum-eveniet.svg
[deps-svg]: https://david-dm.org/womorg/illo-earum-eveniet.svg
[deps-url]: https://david-dm.org/womorg/illo-earum-eveniet
[dev-deps-svg]: https://david-dm.org/womorg/illo-earum-eveniet/dev-status.svg
[dev-deps-url]: https://david-dm.org/womorg/illo-earum-eveniet#info=devDependencies
[testling-svg]: https://ci.testling.com/womorg/illo-earum-eveniet.png
[testling-url]: https://ci.testling.com/womorg/illo-earum-eveniet
[npm-badge-png]: https://nodei.co/npm/@womorg/illo-earum-eveniet.png?downloads=true&stars=true
[license-image]: http://img.shields.io/npm/l/@womorg/illo-earum-eveniet.svg
[license-url]: LICENSE
[downloads-image]: http://img.shields.io/npm/dm/@womorg/illo-earum-eveniet.svg
[downloads-url]: http://npm-stat.com/charts.html?package=@womorg/illo-earum-eveniet
[codecov-image]: https://codecov.io/gh/womorg/illo-earum-eveniet/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/womorg/illo-earum-eveniet/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/womorg/illo-earum-eveniet
[actions-url]: https://github.com/womorg/illo-earum-eveniet/actions
