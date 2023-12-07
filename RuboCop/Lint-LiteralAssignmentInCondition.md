Pattern: Literal assignment in condition

Issue: -

## Description

Checks for literal assignments in the conditions of `if`, `while`, and `until`.

## Examples

```ruby
# bad
if x = 42
  do_something
end

# good
if x == 42
  do_something
end

# good
if x = y
  do_something
end
```

## Further Reading

* [RuboCop - Lint/LiteralAssignmentInCondition](https://docs.rubocop.org/rubocop/cops_lint.html#lintliteralassignmentincondition)
