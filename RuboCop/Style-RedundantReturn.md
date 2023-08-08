Pattern: Redundant `return`

Issue: -

## Description

This rule checks for redundant `return` expressions.

## Examples

```ruby
# bad
def some_method(some_arr)
  return some_arr.size
end

# good
def some_method(some_arr)
  some_arr.size
end
```

## Default configuration

Attribute | Value
--- | ---
AllowMultipleReturnValues | false

## Further Reading

* [RuboCop - Style/RedundantReturn](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantreturn)
* [https://github.com/bbatsov/ruby-style-guide#no-explicit-return](https://github.com/bbatsov/ruby-style-guide#no-explicit-return)
