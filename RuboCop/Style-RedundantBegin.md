Pattern: Style/RedundantBegin

Issue: -

## Description

This cop checks for redundant `begin` blocks.

Currently it checks for code like this:

### Example

```ruby
def redundant
  begin
    ala
    bala
  rescue StandardError => e
    something
  end
end

def preferred
  ala
  bala
rescue StandardError => e
  something
end
```

## Further Reading

* [RuboCop - Style/RedundantBegin](https://rubocop.readthedocs.io/en/latest/cops_style/#styleredundantbegin)
* [https://github.com/bbatsov/ruby-style-guide#begin-implicit](https://github.com/bbatsov/ruby-style-guide#begin-implicit)
