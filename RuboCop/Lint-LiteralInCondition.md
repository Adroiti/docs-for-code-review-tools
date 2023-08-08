Pattern: Literal in condition

Issue: -

## Description

This rule checks for literals used as the conditions or as operands in `and`/`or` expressions serving as the conditions of `if`/`while`/`until`.

## Examples

```ruby
# bad

if 20
  do_something
end
```
```ruby
# bad

if some_var && true
  do_something
end
```
```ruby
# good

if some_var && some_condition
  do_something
end
```

## Further Reading

* [RuboCop - Lint/LiteralInCondition](https://docs.rubocop.org/rubocop/cops_lint.html#lintliteralincondition)
