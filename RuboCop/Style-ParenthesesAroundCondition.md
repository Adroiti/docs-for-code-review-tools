Pattern: Unnecessary parentheses around condition

Issue: -

## Description

This rule checks for the presence of superfluous parentheses around the condition of `if`/`unless`/`while`/`until`.

## Examples

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

* [RuboCop - Style/ParenthesesAroundCondition](https://docs.rubocop.org/rubocop/cops_style.html#styleparenthesesaroundcondition)
* [https://github.com/bbatsov/ruby-style-guide#no-parens-around-condition](https://github.com/bbatsov/ruby-style-guide#no-parens-around-condition)
