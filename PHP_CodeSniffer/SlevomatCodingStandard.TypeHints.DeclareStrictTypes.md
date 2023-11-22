Pattern: Inconsistent strict type declaration

Issue: -

## Description

Enforces having `declare(strict_types = 1)` at the top of each PHP file. Allows configuring how many newlines should be between the `<?php` opening tag and the `declare` statement.

Rule provides the following settings:

* `declareOnFirstLine`: requires `declare` on the first line right after `<?php`
* `linesCountBeforeDeclare`: allows to set 0 to N lines to be between `declare` and previous statement. This option is ignored when `declareOnFirstLine` is enabled.
* `linesCountAfterDeclare`: allows to set 0 to N lines to be between `declare` and next statement
* `spacesCountAroundEqualsSign`: allows to set number of required spaces around the `=` operator

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.TypeHints.DeclareStrictTypes](https://github.com/slevomat/coding-standard/blob/master/doc/type-hints.md#slevomatcodingstandardtypehintsdeclarestricttypes-)