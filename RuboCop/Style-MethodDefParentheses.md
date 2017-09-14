Pattern: Method def parentheses

Issue: -

## Description

This cops checks for parentheses around the arguments in method
definitions. Both instance and class/singleton methods are checked.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | require_parentheses
SupportedStyles | require_parentheses, require_no_parentheses, require_no_parentheses_except_multiline

## Further Reading

* [RuboCop - Style/MethodDefParentheses](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemethoddefparentheses)
* [https://github.com/bbatsov/ruby-style-guide#method-parens](https://github.com/bbatsov/ruby-style-guide#method-parens)
