Pattern: Use of `refute(object.respond_to?(:do_something))`

Issue: -

## Description

Enforces the test to use `refute_respond_to(object, :do_something)` over
`refute(object.respond_to?(:do_something))`.

## Examples

``` ruby
# bad
refute(object.respond_to?(:do_something))
refute(object.respond_to?(:do_something), 'message')
refute(respond_to?(:do_something))

# good
refute_respond_to(object, :do_something)
refute_respond_to(object, :do_something, 'message')
refute_respond_to(self, :do_something)
```

## Further Reading

- <https://minitest.rubystyle.guide#refute-respond-to>