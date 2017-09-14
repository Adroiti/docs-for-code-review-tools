Pattern: Malformed numeric literal prefix

Issue: -

## Description

This cop checks for octal, hex, binary and decimal literals using
uppercase prefixes and corrects them to lowercase prefix
or no prefix (in case of decimals). E.g. for octal use `0o` instead of `0` or `0O`.

Can be configured to use `0` only for octal literals using `EnforcedOctalStyle` => `zero_only`

### Example

```ruby
# bad
num = 01234
num = 0O1234
num = 0X12AB
num = 0B10101
num = 0D1234
num = 0d1234

# good - easier to separate digits from the prefix
num = 0o1234
num = 0x12AB
num = 0b10101
num = 1234
```

## Default configuration

Attribute | Value
--- | ---
EnforcedOctalStyle | zero_with_o
SupportedOctalStyles | zero_with_o, zero_only

## Further Reading

* [RuboCop - Style/NumericLiteralPrefix](https://rubocop.readthedocs.io/en/latest/cops_style/#stylenumericliteralprefix)
* [https://github.com/bbatsov/ruby-style-guide#numeric-literal-prefixes](https://github.com/bbatsov/ruby-style-guide#numeric-literal-prefixes)
