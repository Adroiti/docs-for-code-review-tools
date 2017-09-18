Pattern: Use of mutable constant

Issue: -

## Description

This rule checks whether some constant value isn't a mutable literal (e.g. array or hash).

## Examples

```ruby
# bad
CONST = [1, 2, 3]

# good
CONST = [1, 2, 3].freeze
```

## Further Reading

* [RuboCop - Style/MutableConstant](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemutableconstant)
