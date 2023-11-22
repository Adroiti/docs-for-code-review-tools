Pattern: Trailing array comma

Issue: -

## Description

Commas after last element in an array make adding a new element easier and result in a cleaner versioning diff.

This rule enforces trailing commas in multi-line arrays.

Rule provides the following settings:

* `enableAfterHeredoc`: enables/disables trailing commas after HEREDOC/NOWDOC, default based on PHP version.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Arrays.TrailingArrayComma](https://github.com/slevomat/coding-standard/blob/master/doc/arrays.md#slevomatcodingstandardarraystrailingarraycomma-)