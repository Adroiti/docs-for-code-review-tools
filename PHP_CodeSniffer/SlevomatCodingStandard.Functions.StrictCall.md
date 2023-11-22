Pattern: Malformed `$strict` parameter for function

Issue: -

## Description

Some functions have `$strict` parameter. This sniff reports calls to these functions without the parameter or with `$strict = false`.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Functions.StrictCall](https://github.com/slevomat/coding-standard/blob/master/doc/functions.md#slevomatcodingstandardfunctionsstrictcall)
