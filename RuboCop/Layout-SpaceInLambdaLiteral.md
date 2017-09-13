Pattern: Layout/SpaceInLambdaLiteral

Issue: -

## Description

This cop checks for spaces between -> and opening parameter
brace in lambda literals.

### Example

```ruby
EnforcedStyle: require_no_space (default)

  # bad
  a = -> (x, y) { x + y }

  # good
  a = ->(x, y) { x + y }
```
```ruby
EnforcedStyle: require_space

  # bad
  a = ->(x, y) { x + y }

  # good
  a = -> (x, y) { x + y }
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | require_no_space
SupportedStyles | require_no_space, require_space

## Further Reading

* [RuboCop - Layout/SpaceInLambdaLiteral](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutspaceinlambdaliteral)
