Pattern: Use of variable parsing

Issue: -

## Description

Disallows variable parsing inside strings.

Rule provides the following settings:

* `disallowDollarCurlySyntax`: disallows usage of `${...}`, enabled by default.
* `disallowCurlyDollarSyntax`: disallows usage of `{$...}`, disabled by default.
* `disallowSimpleSyntax`: disallows usage of `$...`, disabled by default.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Strings.DisallowVariableParsing](https://github.com/slevomat/coding-standard/blob/master/doc/strings.md#slevomatcodingstandardstringsdisallowvariableparsing)