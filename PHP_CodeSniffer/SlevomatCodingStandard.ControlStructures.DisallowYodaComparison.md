Pattern: Use of Yoda comparison

Issue: -

## Description

[Yoda conditions](https://en.wikipedia.org/wiki/Yoda_conditions) decrease code comprehensibility and readability by switching operands around comparison operators forcing the reader to read the code in an unnatural way.

Rule provides the following settings:

* `alwaysVariableOnRight` (defaults to `false`): moves variables always to right.

`DisallowYodaComparison` looks for and fixes such comparisons not only in `if` statements but in the whole code.

However, if you prefer Yoda conditions, you can use `RequireYodaComparison`.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.ControlStructures.DisallowYodaComparison](https://github.com/slevomat/coding-standard/blob/master/doc/control-structures.md#slevomatcodingstandardcontrolstructuresdisallowyodacomparison-)