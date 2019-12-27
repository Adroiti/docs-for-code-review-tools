Pattern: Forbidden `break`/`continue` variable argument

Issue: -

## Description

Detects using 0 and variable numeric arguments on `break` and `continue` statements.

This sniff checks for:
- Using `break` and/or `continue` with a variable as the numeric argument.
- Using `break` and/or `continue` with a zero - 0 - as the numeric argument.

PHP version 5.4

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ControlStructures.ForbiddenBreakContinueVariableArguments](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ControlStructures/ForbiddenBreakContinueVariableArgumentsSniff.php)