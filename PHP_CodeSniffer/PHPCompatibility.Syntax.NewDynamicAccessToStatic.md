Pattern: Use of dynamic access to static

Issue: -

## Description

Detects dynamic access to static methods and properties, as well as class constants.

As of PHP 5.3, static properties and methods as well as class constants
can be accessed using a dynamic (variable) class name.

PHP version 5.3

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.Syntax.NewDynamicAccessToStatic](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/Syntax/NewDynamicAccessToStaticSniff.php)