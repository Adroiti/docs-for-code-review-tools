Pattern: Passing `$encoding` to `mb_strrpos()` as 3rd argument

Issue: -

## Description

Detects passing `$encoding` to `mb_strrpos()` as 3rd argument.

The `$encoding` parameter was moved from the third position to the fourth in PHP 5.2.0.
For backward compatibility, `$encoding` could be specified as the third parameter, but doing
so is deprecated and will be removed in the future.

Between PHP 5.2 and PHP 7.3, this was a deprecation in documentation only.
As of PHP 7.4, a deprecation warning will be thrown if an encoding is passed as the 3rd
argument.
As of PHP 8, the argument is expected to change to accept an integer only.

PHP version 5.2
PHP version 7.4

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.RemovedMbStrrposEncodingThirdParam](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/RemovedMbStrrposEncodingThirdParamSniff.php)