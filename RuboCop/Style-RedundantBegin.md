Pattern: Redundant `begin` block

Issue: -

## Description

This cop checks for redundant `begin` blocks. Use _implicit begin blocks_ where possible.

### Example

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

* [RuboCop - Style/RedundantBegin](https://rubocop.readthedocs.io/en/latest/cops_style/#styleredundantbegin)
* [https://github.com/bbatsov/ruby-style-guide#begin-implicit](https://github.com/bbatsov/ruby-style-guide#begin-implicit)
