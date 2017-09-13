Pattern: Style/YodaCondition

Issue: -

## Description

This cop checks for Yoda conditions, i.e. comparison operations where
readability is reduced because the operands are not ordered the same
way as they would be ordered in spoken English.

### Example

```ruby
# EnforcedStyle: all_comparison_operators

# bad
99 == foo
"bar" != foo
42 >= foo
10 < bar

# good
foo == 99
foo == "bar"
foo <= 42
bar > 10
```
```ruby
# EnforcedStyle: equality_operators_only

# bad
99 == foo
"bar" != foo

# good
99 >= foo
3 < a && a < 5
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | all_comparison_operators
SupportedStyles | all_comparison_operators, equality_operators_only

## Further Reading

* [RuboCop - Style/YodaCondition](https://rubocop.readthedocs.io/en/latest/cops_style/#styleyodacondition)
* [https://en.wikipedia.org/wiki/Yoda_conditions](https://en.wikipedia.org/wiki/Yoda_conditions)
