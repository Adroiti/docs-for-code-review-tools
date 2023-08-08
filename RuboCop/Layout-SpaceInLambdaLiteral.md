Pattern: Malformed space in lambda literal

Issue: -

## Description

This rule checks for spaces between `->` and opening parameter brace in lambda literals.

## Examples

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

* [RuboCop - Layout/SpaceInLambdaLiteral](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspaceinlambdaliteral)
