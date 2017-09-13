Pattern: Lint/LiteralInInterpolation

Issue: -

## Description

This cop checks for interpolated literals.

### Example

```ruby
# bad

"result is #{10}"
```
```ruby
# good

"result is 10"
```

## Further Reading

* [RuboCop - Lint/LiteralInInterpolation](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintliteralininterpolation)
