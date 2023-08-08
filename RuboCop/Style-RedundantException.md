Pattern: Redundant exception

Issue: -

## Description

This rule checks for `RuntimeError` as the argument of `raise`/`fail`.

## Examples

```ruby
# Bad
raise RuntimeError, 'message'

# Bad
raise RuntimeError.new('message')

# Good - signals a RuntimeError by default
raise 'message'
```

## Further Reading

* [RuboCop - Style/RedundantException](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantexception)
* [https://github.com/bbatsov/ruby-style-guide#no-explicit-runtimeerror](https://github.com/bbatsov/ruby-style-guide#no-explicit-runtimeerror)
