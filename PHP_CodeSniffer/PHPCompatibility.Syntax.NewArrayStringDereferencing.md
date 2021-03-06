Pattern: Use of array string dereferencing

Issue: -

## Description

Detects array and string literal dereferencing.

As of PHP 5.5, array and string literals can now be dereferenced directly to
access individual elements and characters.

As of PHP 7.0, this also works when using curly braces for the dereferencing.
While unclear, this most likely has to do with the Uniform Variable Syntax changes.

PHP version 5.5
PHP version 7.0

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.Syntax.NewArrayStringDereferencing](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/Syntax/NewArrayStringDereferencingSniff.php)