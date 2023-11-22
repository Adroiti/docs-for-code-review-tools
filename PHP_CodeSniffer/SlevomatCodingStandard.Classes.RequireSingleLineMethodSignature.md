Pattern: Missing use of single-line method signature

Issue: -

## Description

Enforces method signature to be on a single line.

Rule provides the following settings:

* `maxLineLength`: specifies max allowed line length. If signature fit on it, it's enforced. Use 0 value to enforce for all methods, regardless of length.

* `includedMethodPatterns`: allows to configure which methods are included in rule detection. This is an array of regular expressions (PCRE) with delimiters. You should not use this with `excludedMethodPatterns`, as it will not work properly.

* `excludedMethodPatterns`: allows to configure which methods are excluded from rule detection. This is an array of regular expressions (PCRE) with delimiters. You should not use this with `includedMethodPatterns`, as it will not work properly.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Classes.RequireSingleLineMethodSignature](https://github.com/slevomat/coding-standard/blob/master/doc/classes.md#slevomatcodingstandardclassesrequiresinglelinemethodsignature-)