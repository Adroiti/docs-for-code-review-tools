Pattern: Missing use of trailing comma in call

Issue: -

## Description

Commas after the last parameter in function or method call make adding a new parameter easier and result in a cleaner versioning diff.

This rule enforces trailing commas in multi-line calls.

This rule provides the following setting:

* `enable`: either to enable or not this rule. By default, it is enabled for PHP versions 7.3 or higher.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Functions.RequireTrailingCommaInCall](https://github.com/slevomat/coding-standard/blob/master/doc/functions.md#slevomatcodingstandardfunctionsrequiretrailingcommaincall-)