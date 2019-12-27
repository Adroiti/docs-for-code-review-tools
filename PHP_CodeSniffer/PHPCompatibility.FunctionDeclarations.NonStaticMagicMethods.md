Pattern: Malformed magic method visibility/properties

Issue: -

## Description

Verifies the use of the correct visibility and static properties of magic methods.

The requirements have always existed, but as of PHP 5.3, a warning will be thrown
when magic methods have the wrong modifiers.

PHP version 5.3

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.FunctionDeclarations.NonStaticMagicMethods](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/FunctionDeclarations/NonStaticMagicMethodsSniff.php)