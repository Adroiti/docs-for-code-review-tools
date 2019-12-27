Pattern: Importing constants/functions via `use`

Issue: -

## Description

Detects importing constants and functions via a `use` statement.

The `use` operator has been extended to support importing functions and
constants in addition to classes. This is achieved via the `use function`
and `use const` constructs, respectively.

PHP version 5.6

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.UseDeclarations.NewUseConstFunction](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/UseDeclarations/NewUseConstFunctionSniff.php)