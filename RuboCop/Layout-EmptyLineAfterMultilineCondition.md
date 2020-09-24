Pattern: Missing empty line after multi-line condition

Issue: -

## Description

This rule enforces empty line after multi-line condition.

## Examples

```ruby
# bad
if multiline &&
  condition
  do_something
end

# good
if multiline &&
  condition

  do_something
end

# bad
case x
when foo,
  bar
  do_something
end

# good
case x
when foo,
  bar

  do_something
end

# bad
begin
  do_something
rescue FooError,
  BarError
  handle_error
end

# good
begin
  do_something
rescue FooError,
  BarError

  handle_error
end
```

## Further Reading

* [RuboCop - Layout/EmptyLineAfterMultilineCondition](https://docs.rubocop.org/rubocop/cops_layout.html#layoutemptylineaftermultilinecondition)