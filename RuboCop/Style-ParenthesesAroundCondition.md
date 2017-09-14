Pattern: Unnecessary parentheses around condition

Issue: -

## Description

This cop checks for the presence of superfluous parentheses around the condition of `if`/`unless`/`while`/`until`.

### Example

```ruby
# bad
if (x > 10)
  # body omitted
end

# good
if x > 10
  # body omitted
end
```

## Default configuration

Attribute | Value
--- | ---
AllowSafeAssignment | true

## Further Reading

* [RuboCop - Style/ParenthesesAroundCondition](https://rubocop.readthedocs.io/en/latest/cops_style/#styleparenthesesaroundcondition)
* [https://github.com/bbatsov/ruby-style-guide#no-parens-around-condition](https://github.com/bbatsov/ruby-style-guide#no-parens-around-condition)
