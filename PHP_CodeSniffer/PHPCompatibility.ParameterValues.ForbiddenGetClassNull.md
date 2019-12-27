Pattern: Passing `null` to `get_class()`

Issue: -

## Description

Passing `null` to `get_class()` is no longer allowed as of PHP 7.2. This will now result in an `E_WARNING` being thrown.

PHP version 7.2

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.ForbiddenGetClassNull](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/ForbiddenGetClassNullSniff.php)