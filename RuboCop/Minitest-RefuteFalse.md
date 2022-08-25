Pattern: Missing use of `refute(object)`

Issue: -

## Description

Enforces the use of `refute(object)` over `assert_equal(false, object)`.

## Examples

``` ruby
# bad
assert_equal(false, actual)
assert_equal(false, actual, 'message')

assert(!test)
assert(!test, 'message')

# good
refute(actual)
refute(actual, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide#refute-false>