Pattern: Use of non-variable for `empty()`

Issue: -

## Description

Verifies that nothing but variables are passed to `empty()`. Prior to PHP 5.5, `empty()` only supported variables; anything else resulted in a parse error.

PHP version 5.5

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.LanguageConstructs.NewEmptyNonVariable](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/LanguageConstructs/NewEmptyNonVariableSniff.php)