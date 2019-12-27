Pattern: Use of magic `__autoload()`

Issue: -

## Description

Detects declaration of the magic `__autoload()` method. This method has been deprecated in PHP 7.2 in favor of `spl_autoload_register()`.

PHP version 7.2

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.FunctionNameRestrictions.RemovedMagicAutoload](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/FunctionNameRestrictions/RemovedMagicAutoloadSniff.php)