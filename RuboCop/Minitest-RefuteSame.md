Pattern: Missing use of `refute_same(expected, object)`

Issue: -

## Description

Enforces the use of `refute_same(expected, object)` over
`refute(expected.equal?(actual))`.

Use `refute_same` only when there is a need to compare by identity.
Otherwise, use `refute_equal`.

## Examples

``` ruby
# bad
refute(expected.equal?(actual))

# good
refute_same(expected, actual)
```

## Further Reading

-   <https://minitest.rubystyle.guide#refute-same>