Pattern: Inconsistent iterator use

Issue: -

## Description

This rule looks for uses of the `for` keyword, or `each` method. The
preferred alternative is set in the _EnforcedStyle_ configuration
parameter. An `each` call with a block on a single line is always
allowed, however.

## Examples

```ruby
# bad
for elem in arr do
  puts elem
end

# good
arr.each { |elem| puts elem }
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | each
SupportedStyles | for, each

## Further Reading

* [RuboCop - Style/For](https://rubocop.readthedocs.io/en/latest/cops_style/#stylefor)
* [https://github.com/bbatsov/ruby-style-guide#no-for-loops](https://github.com/bbatsov/ruby-style-guide#no-for-loops)
