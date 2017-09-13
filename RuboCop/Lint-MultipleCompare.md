Pattern: Lint/MultipleCompare

Issue: -

## Description

In math and Python, we can use `x < y < z` style comparison to compare
multiple value. However, we can't use the comparison in Ruby. However,
the comparison is not syntax error. This cop checks the bad usage of
comparison operators.

### Example

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

* [RuboCop - Lint/MultipleCompare](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintmultiplecompare)
