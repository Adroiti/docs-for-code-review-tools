Pattern: Invalid constant name

Issue: -

## Description

This rule checks whether constant names are written using `SCREAMING_SNAKE_CASE`. To avoid false positives, it ignores cases in which it cannot know
for certain the type of value that would be assigned to a constant.

## Further Reading

* [RuboCop - Naming/ConstantName](https://docs.rubocop.org/rubocop/cops_naming.html#namingconstantname)
* [https://github.com/bbatsov/ruby-style-guide#screaming-snake-case](https://github.com/bbatsov/ruby-style-guide#screaming-snake-case)
