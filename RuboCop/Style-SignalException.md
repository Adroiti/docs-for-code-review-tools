Pattern: Signal exception

Issue: -

## Description

This cop checks for uses of `fail` and `raise`.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | only_raise
SupportedStyles | only_raise, only_fail, semantic

## Further Reading

* [RuboCop - Style/SignalException](https://rubocop.readthedocs.io/en/latest/cops_style/#stylesignalexception)
* [https://github.com/bbatsov/ruby-style-guide#prefer-raise-over-fail](https://github.com/bbatsov/ruby-style-guide#prefer-raise-over-fail)
