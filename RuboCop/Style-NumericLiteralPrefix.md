Pattern: Numeric literal prefix

Issue: -

## Description

This cop checks for octal, hex, binary and decimal literals using
uppercase prefixes and corrects them to lowercase prefix
or no prefix (in case of decimals).
eg. for octal use `0o` instead of `0` or `0O`.

Can be configured to use `0` only for octal literals using
`EnforcedOctalStyle` => `zero_only`

## Default configuration

Attribute | Value
--- | ---
EnforcedOctalStyle | zero_with_o
SupportedOctalStyles | zero_with_o, zero_only

## Further Reading

* [RuboCop - Style/NumericLiteralPrefix](https://rubocop.readthedocs.io/en/latest/cops_style/#stylenumericliteralprefix)
* [https://github.com/bbatsov/ruby-style-guide#numeric-literal-prefixes](https://github.com/bbatsov/ruby-style-guide#numeric-literal-prefixes)
