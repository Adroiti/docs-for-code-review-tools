Pattern: Use of return type declaration

Issue: -

## Description

Detects and verifies the use of return type declarations in function declarations.

Return type declarations are available since PHP 7.0.
- Since PHP 7.1, the `iterable` and `void` pseudo-types are available.
- Since PHP 7.2, the generic `object` type is available.

PHP version 7.0+

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.FunctionDeclarations.NewReturnTypeDeclarations](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/FunctionDeclarations/NewReturnTypeDeclarationsSniff.php)