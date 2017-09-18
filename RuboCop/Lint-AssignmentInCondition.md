Pattern: Assignment in condition

Issue: -

## Description

This rule checks for assignments in the conditions of `if`/`while`/`until`.

## Examples

```ruby
# bad

if some_var = true
  do_something
end
```
```ruby
# good

if some_var == true
  do_something
end
```

## Default configuration

Attribute | Value
--- | ---
AllowSafeAssignment | true

## Further Reading

* [RuboCop - Lint/AssignmentInCondition](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintassignmentincondition)
* [https://github.com/bbatsov/ruby-style-guide#safe-assignment-in-condition](https://github.com/bbatsov/ruby-style-guide#safe-assignment-in-condition)
