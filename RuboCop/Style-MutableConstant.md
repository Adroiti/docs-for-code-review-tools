Pattern: Style/MutableConstant

Issue: -

## Description

This cop checks whether some constant value isn't a
mutable literal (e.g. array or hash).

### Example

```ruby
# bad
CONST = [1, 2, 3]

# good
CONST = [1, 2, 3].freeze
```

## Further Reading

* [RuboCop - Style/MutableConstant](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemutableconstant)
