Pattern: Style/ArrayJoin

Issue: -

## Description

This cop checks for uses of "*" as a substitute for *join*.

Not all cases can reliably checked, due to Ruby's dynamic
types, so we consider only cases when the first argument is an
array literal or the second is a string literal.

## Further Reading

* [RuboCop - Style/ArrayJoin](https://rubocop.readthedocs.io/en/latest/cops_style/#stylearrayjoin)
* [https://github.com/bbatsov/ruby-style-guide#array-join](https://github.com/bbatsov/ruby-style-guide#array-join)
