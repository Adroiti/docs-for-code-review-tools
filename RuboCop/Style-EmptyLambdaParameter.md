Pattern: Empty lambda parameter with parentheses

Issue: -

## Description

This rule checks for parentheses for empty lambda parameters. Parentheses
for empty lambda parameters do not cause syntax errors, but they are
redundant.

## Examples

```ruby
# bad
-> () { do_something }

# good
-> { do_something }

# good
-> (arg) { do_something(arg) }
```

## Further Reading

* [RuboCop - Style/EmptyLambdaParameter](https://rubocop.readthedocs.io/en/latest/cops_style/#styleemptylambdaparameter)
