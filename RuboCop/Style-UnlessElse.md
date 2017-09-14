Pattern: Use of `unless` with `else`

Issue: -

## Description

This cop looks for *unless* expressions with *else* clauses.

### Example

```ruby
# bad
unless success?
  puts 'failure'
else
  puts 'success'
end

# good
if success?
  puts 'success'
else
  puts 'failure'
end
```

## Further Reading

* [RuboCop - Style/UnlessElse](https://rubocop.readthedocs.io/en/latest/cops_style/#styleunlesselse)
* [https://github.com/bbatsov/ruby-style-guide#no-else-with-unless](https://github.com/bbatsov/ruby-style-guide#no-else-with-unless)
