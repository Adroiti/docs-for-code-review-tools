Pattern: Use of deprecated `BigDecimal.new()`

Issue: -

## Description

`BigDecimal.new()` is deprecated since BigDecimal 1.3.3. This rule identifies places where `BigDecimal.new()` can be replaced by `BigDecimal()`.

## Examples

```ruby
# bad
BigDecimal.new(123.456, 3)

# good
BigDecimal(123.456, 3)
```

## Further Reading

* [RuboCop - Lint/BigDecimalNew](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintbigdecimalnew)
