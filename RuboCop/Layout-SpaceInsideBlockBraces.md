Pattern: Malformed space inside block braces

Issue: -

## Description

Checks that block braces have or don't have surrounding space inside
them. For blocks taking parameters, it checks that the
left brace has or doesn't have trailing space depending on
configuration.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | space
SupportedStyles | space, no_space
EnforcedStyleForEmptyBraces | no_space
SupportedStylesForEmptyBraces | space, no_space
SpaceBeforeBlockParameters | true

## Further Reading

* [RuboCop - Layout/SpaceInsideBlockBraces](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspaceinsideblockbraces)
