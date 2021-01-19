Pattern: Malformed usage of `t()`

Issue: -

## Description

Checks the usage of the `t()` function to not escape translatable strings with back
slashes. Also checks that the first argument does not use string concatenation.

## Further Reading

* [PHP_CodeSniffer - Drupal.Semantics.FunctionT](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/Drupal/Sniffs/Semantics/FunctionTSniff.php)