Pattern: Missing use of `next` to skip iteration

Issue: -

## Description

Use `next` to skip iteration instead of a condition at the end.

## Examples

```ruby
# bad
[1, 2].each do |a|
  if a == 1
    puts a
  end
end

# good
[1, 2].each do |a|
  next unless a == 1
  puts a
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | skip_modifier_ifs
MinBodyLength | 3
SupportedStyles | skip_modifier_ifs, always

## Further Reading

* [RuboCop - Style/Next](https://rubocop.readthedocs.io/en/latest/cops_style/#stylenext)
* [https://github.com/bbatsov/ruby-style-guide#no-nested-conditionals](https://github.com/bbatsov/ruby-style-guide#no-nested-conditionals)
