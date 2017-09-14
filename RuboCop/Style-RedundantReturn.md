Pattern: Redundant `return`

Issue: -

## Description

This cop checks for redundant `return` expressions.

### Example

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

* [RuboCop - Style/RedundantReturn](https://rubocop.readthedocs.io/en/latest/cops_style/#styleredundantreturn)
* [https://github.com/bbatsov/ruby-style-guide#no-explicit-return](https://github.com/bbatsov/ruby-style-guide#no-explicit-return)
