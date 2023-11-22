Pattern: Missing use of numeric literal separator

Issue: -

## Description

Requires use of numeric literal separators.

This rule provides the following setting:

* `enable`: either to enable or not this rule. By default, it is enabled for PHP versions 7.4 or higher.
* `minDigitsBeforeDecimalPoint`: the minimum digits before decimal point to require separator.
* `minDigitsAfterDecimalPoint`: the minimum digits after decimal point to require separator.
* `ignoreOctalNumbers`: to ignore octal numbers.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Numbers.RequireNumericLiteralSeparator](https://github.com/slevomat/coding-standard/blob/master/doc/numbers.md#slevomatcodingstandardnumbersrequirenumericliteralseparator)