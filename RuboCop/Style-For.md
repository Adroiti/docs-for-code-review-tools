Pattern: For

Issue: -

## Description

This cop looks for uses of the *for* keyword, or *each* method. The
preferred alternative is set in the EnforcedStyle configuration
parameter. An *each* call with a block on a single line is always
allowed, however.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | each
SupportedStyles | for, each

## Further Reading

* [RuboCop - Style/For](https://rubocop.readthedocs.io/en/latest/cops_style/#stylefor)
* [https://github.com/bbatsov/ruby-style-guide#no-for-loops](https://github.com/bbatsov/ruby-style-guide#no-for-loops)
