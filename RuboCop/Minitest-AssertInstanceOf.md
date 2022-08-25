Pattern: Missing use of `assert_instance_of(Class, object)

Issue: -

## Description

Enforces the test to use `assert_instance_of(Class, object)` over
`assert(object.instance_of?(Class))`.

## Examples

``` ruby
# bad
assert(object.instance_of?(Class))
assert(object.instance_of?(Class), 'message')

# good
assert_instance_of(Class, object)
assert_instance_of(Class, object, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide#assert-instance-of>