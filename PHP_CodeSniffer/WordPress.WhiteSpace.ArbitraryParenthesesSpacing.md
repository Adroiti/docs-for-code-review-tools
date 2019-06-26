Pattern: Malformed spacing for arbitrary parentheses

Issue: -

## Description

Checks & fixed whitespace on the inside of arbitrary parentheses.

Arbitrary parentheses are those which are not owned by a function (call), array or control structure.
Spacing on the outside is not checked on purpose as this would too easily conflict with other spacing rules.

## Further Reading

* [WordPress.WhiteSpace.ArbitraryParenthesesSpacing](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/WhiteSpace/ArbitraryParenthesesSpacingSniff.php)