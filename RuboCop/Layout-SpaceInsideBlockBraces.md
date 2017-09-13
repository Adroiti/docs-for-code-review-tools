Pattern: Layout/SpaceInsideBlockBraces

Issue: -

## Description

Checks that block braces have or don't have surrounding space inside
them on configuration. For blocks taking parameters, it checks that the
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

* [RuboCop - Layout/SpaceInsideBlockBraces](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutspaceinsideblockbraces)
