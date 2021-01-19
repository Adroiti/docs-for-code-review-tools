Pattern: Use of `check_plain()` for `variable_set()`

Issue: -

## Description

Checks that `variable_set()` calls do not run `check_plain()` or other sanitization functions on the value.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.FunctionCalls.VariableSetSanitize](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/FunctionCalls/VariableSetSanitizeSniff.php)