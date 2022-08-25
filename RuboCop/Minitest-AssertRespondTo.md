Pattern: Use of `assert(object.respond_to?(:do_something))`

Issue: -

## Description

Enforces the use of `assert_respond_to(object, :do_something)` over
`assert(object.respond_to?(:do_something))`.

## Examples

``` ruby
# bad
assert(object.respond_to?(:do_something))
assert(object.respond_to?(:do_something), 'message')
assert(respond_to?(:do_something))

# good
assert_respond_to(object, :do_something)
assert_respond_to(object, :do_something, 'message')
assert_respond_to(self, :do_something)
```

## Further Reading

- <https://minitest.rubystyle.guide#assert-responds-to-method>