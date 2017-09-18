Pattern: Redundant `do` after `while` or `until`

Issue: -

## Description

Checks for uses of `do` in multi-line `while/until` statements.

## Examples

```ruby
# bad
while x > 5 do
  # body omitted
end

until x > 5 do
  # body omitted
end

# good
while x > 5
  # body omitted
end

until x > 5
  # body omitted
end
```

## Further Reading

* [RuboCop - Style/WhileUntilDo](https://rubocop.readthedocs.io/en/latest/cops_style/#stylewhileuntildo)
* [https://github.com/bbatsov/ruby-style-guide#no-multiline-while-do](https://github.com/bbatsov/ruby-style-guide#no-multiline-while-do)
