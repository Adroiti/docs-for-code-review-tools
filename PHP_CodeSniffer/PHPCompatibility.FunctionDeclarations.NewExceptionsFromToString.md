Pattern: Throwing exception from `__toString()`

Issue: -

## Description

As of PHP 7.4, throwing exceptions from a `__toString()` method is allowed.

PHP version 7.4

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.FunctionDeclarations.NewExceptionsFromToString](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/FunctionDeclarations/NewExceptionsFromToStringSniff.php)