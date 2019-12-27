Pattern: Forbidden `__toString()` parameter

Issue: -

## Description

As of PHP 5.3, the `__toString()` magic method can no longer accept arguments.

PHP version 5.3

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.FunctionDeclarations.ForbiddenToStringParameters](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/FunctionDeclarations/ForbiddenToStringParametersSniff.php)