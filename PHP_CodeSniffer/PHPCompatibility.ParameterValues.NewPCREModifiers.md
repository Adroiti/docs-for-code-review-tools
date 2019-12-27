Pattern: Use of unsupported PCRE modifier

Issue: -

## Description

Checks for the use of newly added regex modifiers for PCRE functions.

Initially just checks for the PHP 7.2 new `J` modifier.

PHP version 7.2+

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.NewPCREModifiers](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/NewPCREModifiersSniff.php)