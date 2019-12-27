Pattern: Use magic `::class` constant

Issue: -

## Description

Detects usage of the magic `::class` constant introduced in PHP 5.5.

The special `ClassName::class` constant is available as of PHP 5.5.0, and allows
for fully qualified class name resolution at compile time.

PHP version 5.5

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.Constants.NewMagicClassConstant](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/Constants/NewMagicClassConstantSniff.php)