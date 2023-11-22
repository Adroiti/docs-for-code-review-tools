Pattern: Missing multi-line method signature

Issue: -

## Description

Enforces method signature to be split to more lines so each parameter is on its own line.

Rule provides the following settings:

* `minLineLength`: specifies min line length to enforce signature to be split. Use 0 value to enforce for all methods, regardless of length.
* `minParametersCount`: specifies min parameters count to enforce signature to be split.

* `includedMethodPatterns`: allows to configure which methods are included in rule detection. This is an array of regular expressions (PCRE) with delimiters. You should not use this with `excludedMethodPatterns`, as it will not work properly.

* `excludedMethodPatterns`: allows to configure which methods are excluded from rule detection. This is an array of regular expressions (PCRE) with delimiters. You should not use this with `includedMethodPatterns`, as it will not work properly.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Classes.RequireMultiLineMethodSignature](https://github.com/slevomat/coding-standard/blob/master/doc/classes.md#slevomatcodingstandardclassesrequiremultilinemethodsignature-)