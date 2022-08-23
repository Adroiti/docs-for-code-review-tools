Pattern: Missing range parentheses

Issue: -

## Description

Checks that a range literal is enclosed in parentheses when the end of the range is
at a line break.

```ruby
case condition
when 42..
  do_something
end
```

## Examples

```ruby
# bad - Represents `(1..42)`, not endless range.
1..
42

# good - It's incompatible, but your intentions when using endless range may be:
(1..)
42

# good
1..42

# good
(1..42)

# good
(1..
42)
```

## Further Reading

* [RuboCop - Lint/RequireRangeParentheses](https://docs.rubocop.org/rubocop/cops_lint.html#lintrequirerangeparentheses)
