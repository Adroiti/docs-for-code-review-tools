Pattern: Lint/RequireParentheses

Issue: -

## Description

This cop checks for expressions where there is a call to a predicate
method with at least one argument, where no parentheses are used around
the parameter list, and a boolean operator, && or ||, is used in the
last argument.

The idea behind warning for these constructs is that the user might
be under the impression that the return value from the method call is
an operand of &&/||.

### Example

```ruby
# bad

if day.is? :tuesday && month == :jan
  ...
end
```
```ruby
# good

if day.is?(:tuesday) && month == :jan
```

## Further Reading

* [RuboCop - Lint/RequireParentheses](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintrequireparentheses)
