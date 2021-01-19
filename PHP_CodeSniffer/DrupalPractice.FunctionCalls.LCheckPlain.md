Pattern: Use of `check_plain()` on first arg of `l()`

Issue: -

## Description

The first argument of the `l()` function should not be `check_plain()`'ed. `l()` will sanitize it for you by default.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.FunctionCalls.LCheckPlain](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/FunctionCalls/LCheckPlainSniff.php)