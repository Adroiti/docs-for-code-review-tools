Pattern: Unnecessary ternary operator

Issue: -

## Description

Reports useless ternary operator where both branches return `true` or `false`.

Rule provides the following settings:

* `assumeAllConditionExpressionsAreAlreadyBoolean` (defaults to `false`).

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.ControlStructures.UselessTernaryOperator](https://github.com/slevomat/coding-standard/blob/master/doc/control-structures.md#slevomatcodingstandardcontrolstructuresuselessternaryoperator-)