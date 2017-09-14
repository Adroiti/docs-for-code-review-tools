Pattern: Use of `Proc.new`

Issue: -

## Description

This cop checks for uses of `Proc.new` where `proc` would be more appropriate.

### Example

```ruby
# bad
p = Proc.new { |n| puts n }

# good
p = proc { |n| puts n }
```

## Further Reading

* [RuboCop - Style/Proc](https://rubocop.readthedocs.io/en/latest/cops_style/#styleproc)
* [https://github.com/bbatsov/ruby-style-guide#proc](https://github.com/bbatsov/ruby-style-guide#proc)
