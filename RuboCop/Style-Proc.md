Pattern: Use of `Proc.new`

Issue: -

## Description

This rule checks for uses of `Proc.new` where `proc` would be more appropriate.

## Examples

```ruby
# bad
p = Proc.new { |n| puts n }

# good
p = proc { |n| puts n }
```

## Further Reading

* [RuboCop - Style/Proc](https://docs.rubocop.org/rubocop/cops_style.html#styleproc)
* [https://github.com/bbatsov/ruby-style-guide#proc](https://github.com/bbatsov/ruby-style-guide#proc)
