Pattern: Unnecessary `check_plain()` for placeholder

Issue: -

## Description

Checks that `@` and `%` placeholders in `t()`/`watchdog()` are not escaped twice with `check_plain()`.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.FunctionCalls.TCheckPlain](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/FunctionCalls/TCheckPlainSniff.php)