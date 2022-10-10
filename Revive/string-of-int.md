Pattern: Dubious conversion of integer to string

Issue: -

## Description

Explicit type conversion `string(i)` where `i` has an integer type other than `rune` might behave not as expected by the developer (e.g. `string(42)` is not `"42"`). This rule spot that kind of suspicious conversions.

## Further Reading

* [Revive - string-of-int](https://revive.run/r#string-of-int)