Pattern: Missing use of explicit assertion

Issue: -

## Description

Requires assertion via `assert` instead of inline documentation comments.

Rule provides the following settings:

* `enableIntegerRanges` (defaults to `false`): enables support for `positive-int`, `negative-int` and `int<0, 100>`.
* `enableAdvancedStringTypes` (defaults to `false`): enables support for `callable-string`, `numeric-string` and `non-empty-string`.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.PHP.RequireExplicitAssertion](https://github.com/slevomat/coding-standard/blob/master/doc/php.md#slevomatcodingstandardphprequireexplicitassertion-)