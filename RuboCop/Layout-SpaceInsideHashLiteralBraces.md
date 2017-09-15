Pattern: Malformed space inside hash literal braces

Issue: -

## Description

Checks that braces used for hash literals have or don't have surrounding space depending on configuration.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | space
SupportedStyles | space, no_space, compact
EnforcedStyleForEmptyBraces | no_space
SupportedStylesForEmptyBraces | space, no_space

## Further Reading

* [RuboCop - Layout/SpaceInsideHashLiteralBraces](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutspaceinsidehashliteralbraces)
* [https://github.com/bbatsov/ruby-style-guide#spaces-operators](https://github.com/bbatsov/ruby-style-guide#spaces-operators)
