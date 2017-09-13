Pattern: Style/FormatString

Issue: -

## Description

This cop enforces the use of a single string formatting utility.
Valid options include Kernel#format, Kernel#sprintf and String#%.

The detection of String#% cannot be implemented in a reliable
manner for all cases, so only two scenarios are considered -
if the first argument is a string literal and if the second
argument is an array literal.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | format
SupportedStyles | format, sprintf, percent

## Further Reading

* [RuboCop - Style/FormatString](https://rubocop.readthedocs.io/en/latest/cops_style/#styleformatstring)
* [https://github.com/bbatsov/ruby-style-guide#sprintf](https://github.com/bbatsov/ruby-style-guide#sprintf)
