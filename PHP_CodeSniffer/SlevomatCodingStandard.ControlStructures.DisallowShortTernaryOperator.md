Pattern: Use of `?:`

Issue: -

## Description

Disallows short ternary operator `?:`.

Rule provides the following settings:

* `fixable`: the rule is fixable by default, however in strict code it makes sense to forbid this weakly typed form of ternary altogether, you can disable fixability with this option.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.ControlStructures.DisallowShortTernaryOperator](https://github.com/slevomat/coding-standard/blob/master/doc/control-structures.md#slevomatcodingstandardcontrolstructuresdisallowshortternaryoperator-)