Pattern: Redundant return

Issue: -

## Description

This cop checks for redundant `return` expressions.

It should be extended to handle methods whose body is if/else
or a case expression with a default branch.

### Example

```ruby
def test
  return something
end

def test
  one
  two
  three
  return something
end
```

## Default configuration

Attribute | Value
--- | ---
AllowMultipleReturnValues | false

## Further Reading

* [RuboCop - Style/RedundantReturn](https://rubocop.readthedocs.io/en/latest/cops_style/#styleredundantreturn)
* [https://github.com/bbatsov/ruby-style-guide#no-explicit-return](https://github.com/bbatsov/ruby-style-guide#no-explicit-return)
