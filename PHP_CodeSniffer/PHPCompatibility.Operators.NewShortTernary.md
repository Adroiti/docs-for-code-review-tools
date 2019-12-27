Pattern: Use of short ternary operator

Issue: -

## Description

Detects usage of the short ternary (elvis) operator as introduced in PHP 5.3.

Performs checks on ternary operators, specifically that the middle expression is not omitted for versions that don't support this.

PHP version 5.3

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.Operators.NewShortTernary](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/Operators/NewShortTernarySniff.php)