Pattern: Missing use of multi-line ternary operator

Issue: -

## Description

Ternary operator has to be reformatted to more lines when the line length exceeds the given limit.

Rule provides the following settings:

* `lineLengthLimit` (defaults to `0`)
* `minExpressionsLength` (defaults to `null`): when the expressions after `?` are shorter than this length, the ternary operator does not have to be reformatted.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.ControlStructures.RequireMultiLineTernaryOperator](https://github.com/slevomat/coding-standard/blob/master/doc/control-structures.md#slevomatcodingstandardcontrolstructuresrequiremultilineternaryoperator-)