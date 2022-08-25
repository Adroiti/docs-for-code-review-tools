Pattern: Missing use of `assert_kind_of(Class, object)`

Issue: -

## Description

Enforces the test to use `assert_kind_of(Class, object)` over `assert(object.kind_of?(Class))`.

## Examples

``` ruby
# bad
assert(object.kind_of?(Class))
assert(object.kind_of?(Class), 'message')

# good
assert_kind_of(Class, object)
assert_kind_of(Class, object, 'message')
```

## Further Reading

- <https://github.com/rubocop/minitest-style-guide#assert-kind-of>