Pattern: Interpolation in single quoted string

Issue: -

## Description

This rule checks for interpolation in a single quoted string.

## Examples

```ruby
# bad

foo = 'something with #{interpolation} inside'
```
```ruby
# good

foo = "something with #{interpolation} inside"
```

## Further Reading

* [RuboCop - Lint/InterpolationCheck](https://docs.rubocop.org/rubocop/cops_lint.html#lintinterpolationcheck)
