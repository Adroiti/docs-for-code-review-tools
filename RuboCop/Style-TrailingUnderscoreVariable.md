Pattern: Extra underscore in variable assignment

Issue: -

## Description

This cop checks for extra underscores in variable assignment.

### Example

```ruby
# bad
a, b, _ = foo()
a, b, _, = foo()
a, _, _ = foo()
a, _, _, = foo()

# good
a, b, = foo()
a, = foo()
*a, b, _ = foo()  => We need to know to not include 2 variables in a
a, *b, _ = foo()  => The correction `a, *b, = foo()` is a syntax error

# good if AllowNamedUnderscoreVariables is true
a, b, _something = foo()
```

## Default configuration

Attribute | Value
--- | ---
AllowNamedUnderscoreVariables | true

## Further Reading

* [RuboCop - Style/TrailingUnderscoreVariable](https://rubocop.readthedocs.io/en/latest/cops_style/#styletrailingunderscorevariable)
