Pattern: Missing use of `refute_instance_of(Class, object)`

Issue: -

## Description

Enforces the use of `refute_instance_of(Class, object)` over
`refute(object.instance_of?(Class))`.

## Examples

``` ruby
# bad
refute(object.instance_of?(Class))
refute(object.instance_of?(Class), 'message')

# good
refute_instance_of(Class, object)
refute_instance_of(Class, object, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide#refute-instance-of>