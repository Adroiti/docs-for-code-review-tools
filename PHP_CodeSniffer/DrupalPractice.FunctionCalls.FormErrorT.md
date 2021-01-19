Pattern: Missing `t()` for `form_set_error()`

Issue: -

## Description

Verifies that messages passed to `form_set_error()` run through `t()`.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.FunctionCalls.FormErrorT](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/FunctionCalls/FormErrorTSniff.php)