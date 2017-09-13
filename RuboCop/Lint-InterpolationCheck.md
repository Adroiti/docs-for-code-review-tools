Pattern: Lint/InterpolationCheck

Issue: -

## Description

This cop checks for interpolation in a single quoted string.

### Example

```ruby
# bad

foo = 'something with #{interpolation} inside'
```
```ruby
# good

foo = "something with #{interpolation} inside"
```

## Further Reading

* [RuboCop - Lint/InterpolationCheck](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintinterpolationcheck)
