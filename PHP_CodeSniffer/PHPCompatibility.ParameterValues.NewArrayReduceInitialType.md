Pattern: Passing non-integer `$initial` to `array_reduce()`

Issue: -

## Description

In PHP 5.2 and lower, the `$initial` parameter for `array_reduce()` had to be an integer.

PHP version 5.3

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.NewArrayReduceInitialType](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/NewArrayReduceInitialTypeSniff.php)