Pattern: Use of array type hint syntax

Issue: -

## Description

Disallows usage of array type hint syntax (e.g. `int[]`, `bool[][]`) in phpDocs in favour of generic type hint syntax (eg. `array<int>`, `array<array<bool>>`).

Rule provides the following settings:

* `traversableTypeHints`: helps fixer detect traversable type hints so `\Traversable|int[]` can be converted to `\Traversable<int>`.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.TypeHints.DisallowArrayTypeHintSyntax](https://github.com/slevomat/coding-standard/blob/master/doc/type-hints.md#slevomatcodingstandardtypehintsdisallowarraytypehintsyntax-)