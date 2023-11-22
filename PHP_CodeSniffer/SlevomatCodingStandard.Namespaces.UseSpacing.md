Pattern: Inconsistent `use` spacing

Issue: -

## Description

Enforces configurable number of lines before first `use`, after last `use` and between two different types of `use` (eg. between `use function` and `use const`). Also enforces zero number of lines between same types of `use`.

Rule provides the following settings:

* `linesCountBeforeFirstUse`: allows to configure the number of lines before first `use`.
* `linesCountBetweenUseTypes`: allows to configure the number of lines between two different types of `use`.
* `linesCountAfterLastUse`: allows to configure the number of lines after last `use`.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Namespaces.UseSpacing](https://github.com/slevomat/coding-standard/blob/master/doc/namespaces.md#slevomatcodingstandardnamespacesusespacing-)