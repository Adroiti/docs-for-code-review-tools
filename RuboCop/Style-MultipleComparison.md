Pattern: Comparing variable with multiple items

Issue: -

## Description

This rule checks against comparing a variable with multiple items, where `Array#include?` could be used instead to avoid code repetition.

## Examples

```ruby
# bad
a = 'a'
foo if a == 'a' || a == 'b' || a == 'c'

# good
a = 'a'
foo if ['a', 'b', 'c'].include?(a)
```

## Further Reading

* [RuboCop - Style/MultipleComparison](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemultiplecomparison)
