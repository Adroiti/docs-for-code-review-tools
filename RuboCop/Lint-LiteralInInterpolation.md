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

* [RuboCop - Lint/LiteralInInterpolation](https://docs.rubocop.org/rubocop/cops_lint.html#lintliteralininterpolation)
