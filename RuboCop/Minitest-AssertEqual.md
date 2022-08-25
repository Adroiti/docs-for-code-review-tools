Pattern: Use of `assert(expected == actual)`

Issue: -

## Description

Enforces the use of `assert_equal(expected, actual)` over `assert(expected == actual)`.

## Examples

``` ruby
# bad
assert("rubocop-minitest" == actual)

# good
assert_equal("rubocop-minitest", actual)
```

## Further Reading

- <https://minitest.rubystyle.guide#assert-equal-arguments-order>