Pattern: Numbered parameter assignment

Issue: -

## Description

This rule checks for uses of numbered parameter assignment.

## Examples

```ruby
# bad
_1 = :value

# good
non_numbered_parameter_name = :value
```

## Further Reading

* [RuboCop - Lint/NumberedParameterAssignment](https://docs.rubocop.org/rubocop/cops_lint.html#lintnumberedparameterassignment)
