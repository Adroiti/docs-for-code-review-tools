Pattern: Malformed argument for `assert_equal`

Issue: -

## Description

Enforces correct order of expected and actual arguments for `assert_equal`.

## Examples

``` ruby
# bad
assert_equal foo, 2
assert_equal foo, [1, 2]
assert_equal foo, [1, 2], 'message'

# good
assert_equal 2, foo
assert_equal [1, 2], foo
assert_equal [1, 2], foo, 'message'
```

## Further Reading

- <https://minitest.rubystyle.guide/#assert-equal-arguments-order>