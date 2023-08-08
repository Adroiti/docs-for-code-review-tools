Pattern: Use of `unless` with `else`

Issue: -

## Description

This rule looks for *unless* expressions with *else* clauses.

## Examples

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

* [RuboCop - Style/UnlessElse](https://docs.rubocop.org/rubocop/cops_style.html#styleunlesselse)
* [https://github.com/bbatsov/ruby-style-guide#no-else-with-unless](https://github.com/bbatsov/ruby-style-guide#no-else-with-unless)
