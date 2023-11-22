Pattern: Inconsistent union type hint format

Issue: -

## Description

Checks format of union type hints.

Rule provides the following settings:

* `enable`: either to enable or not this rule. By default, it is enabled for PHP versions 8.0 or higher.
* `withSpaces`: `yes` requires spaces around `|`, `no` requires no space around `|`. None is set by default so both are enabled.
* `shortNullable`: `yes` requires usage of `?` for nullable type hint, `no` disallows it. None is set by default so both are enabled.
* `nullPosition`: `first` requires `null` on first position in the type hint, `last` requires last position. None is set by default so `null` can be everywhere.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.TypeHints.UnionTypeHintFormat](https://github.com/slevomat/coding-standard/blob/master/doc/type-hints.md#slevomatcodingstandardtypehintsuniontypehintformat-)