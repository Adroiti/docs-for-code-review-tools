Pattern: Passing the `$category` as a string to `setlocale()`

Issue: -

## Description

Detects passing a string literal as `$category` to `setlocale()`.

Support for the category parameter passed as a string has been removed. Only `LC_*` constants can be used as of PHP 7.0.0.

PHP version 4.2
PHP version 7.0

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.RemovedSetlocaleString](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/RemovedSetlocaleStringSniff.php)