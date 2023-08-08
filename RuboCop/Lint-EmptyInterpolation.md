Pattern: Empty interpolation

Issue: -

## Description

This rule checks for empty interpolation.

## Examples

```ruby
# bad

"result is #{}"
```
```ruby
# good

"result is #{some_result}"
```

## Further Reading

* [RuboCop - Lint/EmptyInterpolation](https://docs.rubocop.org/rubocop/cops_lint.html#lintemptyinterpolation)
