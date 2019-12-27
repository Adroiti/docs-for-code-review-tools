Pattern: Use of `foreach` expression referencing

Issue: -

## Description

Detects `foreach` expression referencing.

Before PHP 5.5.0, referencing `$value` in a `foreach` was only possible
if the iterated array could be referenced (i.e. if it is a variable).

PHP version 5.5

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ControlStructures.NewForeachExpressionReferencing](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ControlStructures/NewForeachExpressionReferencingSniff.php)