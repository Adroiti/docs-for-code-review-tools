Pattern: Missing use of trailing comma in declaration

Issue: -

## Description

Commas after the last parameter in function or method declaration make adding a new parameter easier and result in a cleaner versioning diff.

This rule enforces trailing commas in multi-line declarations.

This rule provides the following setting:

* `enable`: either to enable or not this rule. By default, it is enabled for PHP versions 8.0 or higher.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Functions.RequireTrailingCommaInDeclaration](https://github.com/slevomat/coding-standard/blob/master/doc/functions.md#slevomatcodingstandardfunctionsrequiretrailingcommaindeclaration-)