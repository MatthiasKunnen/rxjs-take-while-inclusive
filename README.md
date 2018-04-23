# TakeWhileInclusive
A takeWhile variant which also emits the value not satisfying the predicate
before completing.

```TypeScript
takeWhileInclusive(predicate)
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
