Pattern: Inconsistent use of hash method

Issue: -

## Description

This rule (by default) checks for uses of methods `Hash#has_key?` and `Hash#has_value?` where it enforces `Hash#key?` and `Hash#value?`. It is configurable to enforce the inverse, using `verbose` method names also.

## Examples

```ruby
# EnforcedStyle: short (default)

# bad
Hash#has_key?
Hash#has_value?

# good
Hash#key?
Hash#value?
```
```ruby
# EnforcedStyle: verbose

# bad
Hash#key?
Hash#value?

# good
Hash#has_key?
Hash#has_value?
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | short
SupportedStyles | short, verbose

## Further Reading

* [RuboCop - Style/PreferredHashMethods](https://docs.rubocop.org/rubocop/cops_style.html#stylepreferredhashmethods)
* [https://github.com/bbatsov/ruby-style-guide#hash-key](https://github.com/bbatsov/ruby-style-guide#hash-key)
