Pattern: Unused function parameter

Issue: -

## Description

Checks the for unused function parameters.

This rule checks that all function parameters are used in the function body.
One exception is made for empty function bodies or function bodies that only
contain comments. This could be useful for the classes that implement an
interface that defines multiple methods but the implementation only needs some
of them.

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.UnusedFunctionParameter](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/UnusedFunctionParameterSniff.php)