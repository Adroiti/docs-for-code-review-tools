Pattern: Redundant `begin` block

Issue: -

## Description

This rule checks for redundant `begin` blocks. Use _implicit begin blocks_ where possible.

## Examples

```ruby
# bad
def foo
  begin
    # main logic goes here
  rescue
    # failure handling goes here
  end
end

# good
def foo
  # main logic goes here
rescue
  # failure handling goes here
end
```

## Further Reading

* [RuboCop - Style/RedundantBegin](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantbegin)
* [https://github.com/bbatsov/ruby-style-guide#begin-implicit](https://github.com/bbatsov/ruby-style-guide#begin-implicit)
