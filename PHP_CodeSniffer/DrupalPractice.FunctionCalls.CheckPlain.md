Pattern: Use of `check_plain()` on literal

Issue: -

## Description

Checks that `check_plain()` is not used on literal strings, because they cannot contain user provided text.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.FunctionCalls.CheckPlain](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/FunctionCalls/CheckPlainSniff.php)