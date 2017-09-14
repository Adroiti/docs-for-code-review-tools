Pattern: Numeric literals

Issue: -

## Description

This cop checks for big numeric literals without _ between groups
of digits in them.

### Example

```ruby
# bad

1000000
1_00_000
1_0000

# good

1_000_000
1000

# good unless Strict is set

10_000_00 # typical representation of $10,000 in cents
```

## Default configuration

Attribute | Value
--- | ---
MinDigits | 5
Strict | false

## Further Reading

* [RuboCop - Style/NumericLiterals](https://rubocop.readthedocs.io/en/latest/cops_style/#stylenumericliterals)
* [https://github.com/bbatsov/ruby-style-guide#underscores-in-numerics](https://github.com/bbatsov/ruby-style-guide#underscores-in-numerics)
