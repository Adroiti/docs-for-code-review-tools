Pattern: Missing use of `refute_equal(expected, object)`

Issue: -

## Description

Enforces the use of `refute_equal(expected, object)` over
`assert(expected != actual)` or `assert(! expected == actual)`.

## Examples

``` ruby
# bad
assert("rubocop-minitest" != actual)
assert(! "rubocop-minitest" == actual)

# good
refute_equal("rubocop-minitest", actual)
```

## Further Reading

- <https://minitest.rubystyle.guide#refute-equal>