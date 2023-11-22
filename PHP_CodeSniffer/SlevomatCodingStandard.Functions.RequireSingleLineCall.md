Pattern: Missing use of single-line call

Issue: -

## Description

Enforces function call to be on a single line.

Rule provides the following settings:

* `maxLineLength`: specifies max allowed line length. If call would fit on it, it's enforced. Use 0 value to enforce for all calls, regardless of length.
* `ignoreWithComplexParameter` (defaults to `true`): ignores calls with arrays, closures, arrow functions and nested calls.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Functions.RequireSingleLineCall](https://github.com/slevomat/coding-standard/blob/master/doc/functions.md#slevomatcodingstandardfunctionsrequiresinglelinecall-)