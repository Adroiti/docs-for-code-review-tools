Pattern: Malformed `use` spacing

Issue: -

## Description

Enforces configurable number of lines before first `use`, after last `use` and between two `use` statements.

Rule provides the following settings:

* `linesCountBeforeFirstUse`: allows to configure the number of lines before first `use`.
* `linesCountBeforeFirstUseWhenFirstInClass`: allows to configure the number of lines before first `use` when the `use` is the first statement in the class.
* `linesCountBetweenUses`: allows to configure the number of lines between two `use` statements.
* `linesCountAfterLastUse`: allows to configure the number of lines after last `use`.
* `linesCountAfterLastUseWhenLastInClass`: allows to configure the number of lines after last `use` when the `use` is the last statement in the class.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Classes.TraitUseSpacing](https://github.com/slevomat/coding-standard/blob/master/doc/classes.md#slevomatcodingstandardclassestraitusespacing-)