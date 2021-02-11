Pattern: or-assignment to a constant

Issue: -

## Description

Constants should always be assigned in the same location. And its value should always be the same. If constants are assigned in multiple locations, the result may vary depending on the order of `require`.

Also, if you already have such an implementation, auto-correction may change the result.

## Examples

```ruby
# bad
CONST ||= 1

# good
CONST = 1
```

## Further Reading

* [RuboCop - Lint/OrAssignmentToConstant](https://docs.rubocop.org/rubocop/cops_lint.html#lintorassignmenttoconstant)
