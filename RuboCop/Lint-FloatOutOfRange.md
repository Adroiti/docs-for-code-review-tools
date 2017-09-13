Pattern: Lint/FloatOutOfRange

Issue: -

## Description

This cop identifies Float literals which are, like, really really really
really really really really really big. Too big. No-one needs Floats
that big. If you need a float that big, something is wrong with you.

### Example

```ruby
# bad

float = 3.0e400
```
```ruby
# good

float = 42.9
```

## Further Reading

* [RuboCop - Lint/FloatOutOfRange](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintfloatoutofrange)
