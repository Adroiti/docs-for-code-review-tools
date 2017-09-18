Pattern: Improper use of `fail` or `raise`

Issue: -

## Description

This rule checks for uses of `fail` and `raise`. By default, it prefers `raise` over `fail` for exceptions.

## Examples

```ruby
# bad
fail SomeException, 'message'

# good
raise SomeException, 'message'
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | only_raise
SupportedStyles | only_raise, only_fail, semantic

## Further Reading

* [RuboCop - Style/SignalException](https://rubocop.readthedocs.io/en/latest/cops_style/#stylesignalexception)
* [https://github.com/bbatsov/ruby-style-guide#prefer-raise-over-fail](https://github.com/bbatsov/ruby-style-guide#prefer-raise-over-fail)
