Pattern: Float out of range

Issue: -

## Description

This rule identifies Float literals which are out of range.

## Examples

```ruby
# bad

float = 3.0e400
```
```ruby
# good

float = 42.9
```

## Further Reading

* [RuboCop - Lint/FloatOutOfRange](https://docs.rubocop.org/rubocop/cops_lint.html#lintfloatoutofrange)
