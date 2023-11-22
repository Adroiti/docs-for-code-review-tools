Pattern: Missing use of trailing comma in closure use

Issue: -

## Description

Commas after the last inherited variable in multi-line `use` of closure declaration make adding a new variable easier and result in a cleaner versioning diff.

This rule enforces trailing commas in multi-line declarations.

This rule provides the following setting:

* `enable`: either to enable or not this rule. By default, it is enabled for PHP versions 8.0 or higher.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Functions.RequireTrailingCommaInClosureUse](https://github.com/slevomat/coding-standard/blob/master/doc/functions.md#slevomatcodingstandardfunctionsrequiretrailingcommainclosureuse-)