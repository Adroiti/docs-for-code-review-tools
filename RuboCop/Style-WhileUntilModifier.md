Pattern: Missing use of `while/until`

Issue: -

## Description

Checks for `while` and `until` statements that would fit on one line if written as a modifier `while/until`. The maximum line length is configurable.

## Default configuration

Attribute | Value
--- | ---
MaxLineLength | 80

## Further Reading

* [RuboCop - Style/WhileUntilModifier](https://docs.rubocop.org/rubocop/cops_style.html#stylewhileuntilmodifier)
* [https://github.com/bbatsov/ruby-style-guide#while-as-a-modifier](https://github.com/bbatsov/ruby-style-guide#while-as-a-modifier)
