Pattern: Use of `assert(object.empty?)`

Issue: -

## Description

Enforces the test to use `assert_empty` instead of using
`assert(object.empty?)`.

## Examples

``` ruby
# bad
assert(object.empty?)
assert(object.empty?, 'message')

# good
assert_empty(object)
assert_empty(object, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide#assert-empty>