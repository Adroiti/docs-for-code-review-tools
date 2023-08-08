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

* [RuboCop - Lint/BigDecimalNew](https://docs.rubocop.org/rubocop/cops_lint.html#lintbigdecimalnew)
