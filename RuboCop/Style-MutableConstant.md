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

* [RuboCop - Style/MutableConstant](https://docs.rubocop.org/rubocop/cops_style.html#stylemutableconstant)
