Pattern: Forbidden variable name in closure use

Issue: -

## Description

Detects variable names forbidden to be used in closure `use` statements.

Variables bound to a closure via the `use` construct cannot use the same name
as any superglobals, `$this`, or any parameter since PHP 7.1.

PHP version 7.1

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.FunctionDeclarations.ForbiddenVariableNamesInClosureUse](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/FunctionDeclarations/ForbiddenVariableNamesInClosureUseSniff.php)