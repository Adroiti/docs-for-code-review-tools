Pattern: Malformed space inside string interpolation

Issue: -

## Description

This rule checks for whitespace within string interpolations.

## Examples

```ruby
# Good if EnforcedStyle is no_space, bad if space.
   var = "This is the #{no_space} example"

# Good if EnforceStyle is space, bad if no_space.
   var = "This is the #{ space } example"
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | no_space
SupportedStyles | space, no_space

## Further Reading

* [RuboCop - Layout/SpaceInsideStringInterpolation](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspaceinsidestringinterpolation)
* [https://github.com/bbatsov/ruby-style-guide#string-interpolation](https://github.com/bbatsov/ruby-style-guide#string-interpolation)
