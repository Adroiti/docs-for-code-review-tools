Pattern: Naming/ConstantName

Issue: -

## Description

This cop checks whether constant names are written using
SCREAMING_SNAKE_CASE.

To avoid false positives, it ignores cases in which we cannot know
for certain the type of value that would be assigned to a constant.

## Further Reading

* [RuboCop - Naming/ConstantName](https://rubocop.readthedocs.io/en/latest/cops_naming/#namingconstantname)
* [https://github.com/bbatsov/ruby-style-guide#screaming-snake-case](https://github.com/bbatsov/ruby-style-guide#screaming-snake-case)
