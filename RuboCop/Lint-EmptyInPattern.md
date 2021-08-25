Pattern: Use of `in` pattern branch without body

Issue: -

## Description

Checks for the presence of `in` pattern branches without a body.

## Examples

```ruby
# bad
case condition
in [a]
  do_something
in [a, b]
end

# good
case condition
in [a]
  do_something
in [a, b]
  nil
end
```

## Further Reading

* [RuboCop - Lint/EmptyInPattern](https://docs.rubocop.org/rubocop/cops_lint.html#lintemptyinpattern)
