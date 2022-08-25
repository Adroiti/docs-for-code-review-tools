Pattern: Use of `refute(object.empty?)`

Issue: -

## Description

Enforces to use `refute_empty` instead of using `refute(object.empty?)`.

## Examples

``` ruby
# bad
refute(object.empty?)
refute(object.empty?, 'message')

# good
refute_empty(object)
refute_empty(object, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide#refute-empty>