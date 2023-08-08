Pattern: Mismatched format parameters

Issue: -

## Description

This lint sees if there is a mismatch between the number of expected fields for `format`/`sprintf`/`#%` and what is actually passed as arguments.

## Examples

```ruby
# bad

format('A value: %s and another: %i', a_value)
```
```ruby
# good

format('A value: %s and another: %i', a_value, another)
```

## Further Reading

* [RuboCop - Lint/FormatParameterMismatch](https://docs.rubocop.org/rubocop/cops_lint.html#lintformatparametermismatch)
