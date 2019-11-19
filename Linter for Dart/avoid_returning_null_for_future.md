Pattern: Returning null for `Future`

Issue: -

## Description

It is almost always wrong to return `null` for a `Future`. Most of the time the
developer simply forgot to put an `async` keyword on the function.

## Further Reading

* [Linter for Dart - avoid_returning_null_for_future](https://dart-lang.github.io/linter/lints/avoid_returning_null_for_future.html)