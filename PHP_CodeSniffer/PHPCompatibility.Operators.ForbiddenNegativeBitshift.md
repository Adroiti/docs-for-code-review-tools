Pattern: Use of negative bit-shift

Issue: -

## Description

Bitwise shifts by negative number will throw an ArithmeticError since PHP 7.0.

PHP version 7.0

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.Operators.ForbiddenNegativeBitshift](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/Operators/ForbiddenNegativeBitshiftSniff.php)