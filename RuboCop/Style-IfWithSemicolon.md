Pattern: Use of `if x; ...` instead of ternary

Issue: -

## Description

Checks for uses of semicolon in `if` statements. Use the ternary operator instead. 

## Examples

```ruby
# bad
result = if some_condition; something else something_else end

# good
result = some_condition ? something : something_else
```

## Further Reading

* [RuboCop - Style/IfWithSemicolon](https://rubocop.readthedocs.io/en/latest/cops_style/#styleifwithsemicolon)
* [https://github.com/bbatsov/ruby-style-guide#no-semicolon-ifs](https://github.com/bbatsov/ruby-style-guide#no-semicolon-ifs)
