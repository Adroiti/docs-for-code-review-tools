Pattern: Odd `else` layout

Issue: -

## Description

This rule checks for odd else block layout - like having an expression on the same line as the `else` keyword, which is usually a mistake.

## Examples

```ruby
# bad

if something
  ...
else do_this
  do_that
end
```
```ruby
# good

if something
  ...
else
  do_this
  do_that
end
```

## Further Reading

* [RuboCop - Lint/ElseLayout](https://docs.rubocop.org/rubocop/cops_lint.html#lintelselayout)
