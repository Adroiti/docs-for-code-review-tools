Pattern: Float out of range

Issue: -

## Description

This cop identifies Float literals which are out of range.

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
