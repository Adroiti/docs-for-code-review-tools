Pattern: Lint/EmptyInterpolation

Issue: -

## Description

This cop checks for empty interpolation.

### Example

```ruby
# bad

"result is #{}"
```
```ruby
# good

"result is #{some_result}"
```

## Further Reading

* [RuboCop - Lint/EmptyInterpolation](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintemptyinterpolation)
