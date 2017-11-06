Pattern: Unreachable code

Issue: -

## Description

Unreachable code can never be executed because there exists no control flow path to the code from the rest of the program. It is generally considered undesirable for a number of reasons, including increased code size and increased time and effort for maintenance. Consider deleting unused code to resolve this issue.

## Further Reading

* [PHP_CodeSniffer - Squiz.PHP.NonExecutableCode](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/PHP/NonExecutableCodeSniff.php)