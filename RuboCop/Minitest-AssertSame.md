Pattern: Missing use of `assert_same(expected, actual)`

Issue: -

## Description

Enforces the use of `assert_same(expected, actual)` over
`assert(expected.equal?(actual))`.

Use `assert_same` only when there is a need to compare by identity.
Otherwise, use `assert_equal`.

## Examples

``` ruby
# bad
assert(expected.equal?(actual))

# good
assert_same(expected, actual)
```

## Further Reading

-   <https://minitest.rubystyle.guide#assert-same>