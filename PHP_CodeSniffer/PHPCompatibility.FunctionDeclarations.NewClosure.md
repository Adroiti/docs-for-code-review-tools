Pattern: Malformed closure or anonymous function

Issue: -

## Description

Detects closures and verifies that the features used are supported.

Version based checks:
- Closures are available since PHP 5.3.
- Closures can be declared as `static` since PHP 5.4.
- Closures can use the `$this` variable within a class context since PHP 5.4.
- Closures can use `self`/`parent`/`static` since PHP 5.4.

Version independent checks:
- Static closures don't have access to the `$this` variable.
- Closures declared outside of a class context don't have access to the `$this`
  variable unless bound to an object.

PHP version 5.3
PHP version 5.4

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.FunctionDeclarations.NewClosure](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/FunctionDeclarations/NewClosureSniff.php)