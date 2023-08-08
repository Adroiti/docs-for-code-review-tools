Pattern: Malformed parentheses in method definition

Issue: -

## Description

This rule checks for parentheses around the arguments in method definitions. Both instance and class/singleton methods are checked.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | require_parentheses
SupportedStyles | require_parentheses, require_no_parentheses, require_no_parentheses_except_multiline

## Further Reading

* [RuboCop - Style/MethodDefParentheses](https://docs.rubocop.org/rubocop/cops_style.html#stylemethoddefparentheses)
* [https://github.com/bbatsov/ruby-style-guide#method-parens](https://github.com/bbatsov/ruby-style-guide#method-parens)
