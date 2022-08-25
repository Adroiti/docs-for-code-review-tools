Pattern: Missing use of `refute_kind_of(Class, object)`

Issue: -

## Description

Enforces the use of `refute_kind_of(Class, object)` over
`refute(object.kind_of?(Class))`.

## Examples

``` ruby
# bad
refute(object.kind_of?(Class))
refute(object.kind_of?(Class), 'message')

# good
refute_kind_of(Class, object)
refute_kind_of(Class, object, 'message')
```

## Further Reading

- <https://github.com/rubocop/minitest-style-guide#refute-kind-of>