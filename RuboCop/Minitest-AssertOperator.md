Pattern: Use of `assert(expected < actual)`

Issue: -

## Description

Enforces the use of `assert_operator(expected, :<, actual)` over `assert(expected < actual)`.

## Examples

``` ruby
# bad
assert(expected < actual)

# good
assert_operator(expected, :<, actual)
```