Pattern: Useless `else` in `begin..end`

Issue: -

## Description

This rule checks for useless `else` in `begin..end` without `rescue`.

## Examples

```ruby
# bad

begin
  do_something
else
  do_something_else # This will never be run.
end
```
```ruby
# good

begin
  do_something
rescue
  handle_errors
else
  do_something_else
end
```

## Further Reading

* [RuboCop - Lint/UselessElseWithoutRescue](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintuselesselsewithoutrescue)
