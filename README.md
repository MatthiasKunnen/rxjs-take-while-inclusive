[![npm version](https://img.shields.io/npm/v/rxjs-take-while-inclusive.svg?style=for-the-badge)](https://www.npmjs.com/package/rxjs-take-while-inclusive)

__Note: This package is no longer needed as of
[rxjs@6.4.0](https://github.com/ReactiveX/rxjs/blob/master/CHANGELOG.md#640-2019-01-30) as the
operator now takes an extra parameter which when true will also emit the last value.
See [rxjs#4115](https://github.com/ReactiveX/rxjs/pull/4115).__

# TakeWhileInclusive
A takeWhile variant which also emits the value not satisfying the predicate
before completing.

Example usage
```TypeScript
import { takeWhileInclusive } from 'rxjs-take-while-inclusive';
import { interval } from 'rxjs/observable/interval';

 interval(1000).pipe(
    takeWhileInclusive(v => v < 5),
).subscribe(console.log);
// Prints: 0, 1, 2, 3, 4, 5
```

Emits values emitted by the source Observable so long as each value satisfies
the given `predicate`, and then completes after the last emitted value satisfies
the `predicate`.  `takeWhileInclusive` subscribes and begins mirroring the
source Observable. Each value emitted on the source is emitted then given to the
`predicate` function which returns a boolean, representing a condition to be
satisfied by the source values. The output Observable emits the source values
until such time as the `predicate` returns false, at which point
`takeWhileInclusive` stops mirroring the source Observable and completes the
output Observable.

## Node
This module supports CommonJS, esm5 and esm2015. To use in node see the
following import.

```javascript
const {takeWhileInclusive} = require('rxjs-take-while-inclusive');
```
