Pattern: Duplicate rescue exception

Issue: -

## Description

This rule checks that there are no repeated exceptions used in `rescue` expressions.

## Examples

```ruby
# bad
begin
  something
rescue FirstException
  handle_exception
rescue FirstException
  handle_other_exception
end

# good
begin
  something
rescue FirstException
  handle_exception
rescue SecondException
  handle_other_exception
end
```

## Further Reading

* [RuboCop - Lint/DuplicateRescueException](https://docs.rubocop.org/rubocop/cops_lint.html#lintduplicaterescueexception)
