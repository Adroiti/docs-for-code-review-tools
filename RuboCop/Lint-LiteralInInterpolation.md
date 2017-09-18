Pattern: Literal in interpolation

Issue: -

## Description

This rule checks for interpolated literals.

## Examples

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
