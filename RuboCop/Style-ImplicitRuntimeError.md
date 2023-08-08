Pattern: Implicit runtime error

Issue: -

## Description

This rule checks for `raise` or `fail` statements which do not specify an
explicit exception class. (This raises a `RuntimeError`. Some projects
might prefer to use exception classes which more precisely identify the
nature of the error.)

## Examples

```ruby
# bad
raise 'Error message here'

# good
raise ArgumentError, 'Error message here'
```

## Further Reading

* [RuboCop - Style/ImplicitRuntimeError](https://docs.rubocop.org/rubocop/cops_style.html#styleimplicitruntimeerror)
