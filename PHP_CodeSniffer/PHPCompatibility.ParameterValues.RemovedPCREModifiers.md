Pattern: Use of deprecated PCRE modifier

Issue: -

## Description

Checks for the use of deprecated and removed regex modifiers for PCRE regex functions.

Initially just checks for the `e` modifier, which was deprecated since PHP 5.5
and removed as of PHP 7.0.

PHP version 5.5
PHP version 7.0

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.RemovedPCREModifiers](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/RemovedPCREModifiersSniff.php)