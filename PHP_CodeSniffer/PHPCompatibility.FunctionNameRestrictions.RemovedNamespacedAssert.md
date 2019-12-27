Pattern: Use of namespaced `assert()`

Issue: -

## Description

Detects declaration of a namespaced function called `assert()`.

As of PHP 7.3, a compile-time deprecation warning will be thrown when a function
called `assert()` is declared. In PHP 8 this will become a compile-error.

Methods are unaffected.
Global, non-namespaced, `assert()` function declarations were always a fatal
"function already declared" error, so not the concern of this sniff.

PHP version 7.3

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.FunctionNameRestrictions.RemovedNamespacedAssert](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/FunctionNameRestrictions/RemovedNamespacedAssertSniff.php)