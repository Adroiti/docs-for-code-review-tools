Pattern: Invalid multiple comparison

Issue: -

## Description

In math and Python, you can use `x < y < z` style comparison to compare
multiple value. However, you can't use the comparison in Ruby. However,
the comparison is not syntax error. This rule checks the bad usage of
comparison operators.

## Examples

```ruby
# bad

x < y < z
10 <= x <= 20
```
```ruby
# good

x < y && y < z
10 <= x && x <= 20
```

## Further Reading

* [RuboCop - Lint/MultipleComparison](https://docs.rubocop.org/rubocop/cops_lint.html#lintmultiplecomparison)
