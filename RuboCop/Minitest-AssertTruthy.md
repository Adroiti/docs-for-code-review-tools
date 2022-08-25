Pattern: Use of `assert_equal(true, actual)`

Issue: -

## Description

Enforces the test to use `assert(actual)` instead of using `assert_equal(true, actual)`.

## Examples

``` ruby
# bad
assert_equal(true, actual)
assert_equal(true, actual, 'message')

# good
assert(actual)
assert(actual, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide#assert-truthy>