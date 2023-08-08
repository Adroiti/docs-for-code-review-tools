Pattern: Inconsistent single string formatting

Issue: -

## Description

This rule enforces the use of a single string formatting utility. By default, it favor's the use of `format` over the fairly cryptic `String#%` method.

## Examples

```ruby
# bad
'%d %d' % [20, 10]
# => '20 10'

format('%d %d', 20, 10)
# => '20 10'
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | format
SupportedStyles | format, sprintf, percent

## Further Reading

* [RuboCop - Style/FormatString](https://docs.rubocop.org/rubocop/cops_style.html#styleformatstring)
* [https://github.com/bbatsov/ruby-style-guide#sprintf](https://github.com/bbatsov/ruby-style-guide#sprintf)
