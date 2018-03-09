Pattern: Arbitrary parentheses spacing

Issue: -

## Description

Check & fix whitespace on the inside of arbitrary parentheses.

Arbitrary parentheses are those which are not owned by a function (call), array or control structure.
Spacing on the outside is not checked on purpose as this would too easily conflict with other spacing rules.

## Further Reading

* [PHP_CodeSniffer - Generic.WhiteSpace.ArbitraryParenthesesSpacing](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/WhiteSpace/ArbitraryParenthesesSpacingSniff.php)