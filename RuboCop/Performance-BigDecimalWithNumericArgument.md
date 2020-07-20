Pattern: Use of `BigDecimal` with numeric argument

Issue: -

## Description

Identifies places where numeric argument to `BigDecimal` should be converted to string. Initializing from String is faster than from Numeric for BigDecimal.

## Examples

```ruby
# bad
BigDecimal(1, 2)
BigDecimal(1.2, 3, exception: true)

# good
BigDecimal('1', 2)
BigDecimal('1.2', 3, exception: true)
```

## Further Reading

* [RuboCop - Performance/BigDecimalWithNumericArgument](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancebigdecimalwithnumericargument)