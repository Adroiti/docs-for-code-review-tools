Pattern: Use of sanitization function for `#default_value`

Issue: -

## Description

Checks that sanitization functions such as `check_plain()` are not used on Form API `#default_value` elements. They get escaped automatically.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.FunctionCalls.DefaultValueSanitize](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/FunctionCalls/DefaultValueSanitizeSniff.php)