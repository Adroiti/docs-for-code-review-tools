Pattern: Malformed variable name

Issue: -

## Description

Checks the usage of `variable_get()` in forms and the variable name. All variables defined by your module must be prefixed with your module's name to avoid name collisions with others.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.General.VariableName](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/General/VariableNameSniff.php)