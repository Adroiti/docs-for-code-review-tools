Pattern: Missing use of `assert_includes`

Issue: -

## Description

Enforces the test to use `assert_includes` instead of using `assert(collection.include?(object))`.

## Examples

``` ruby
# bad
assert(collection.include?(object))
assert(collection.include?(object), 'message')

# good
assert_includes(collection, object)
assert_includes(collection, object, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide#assert-includes>