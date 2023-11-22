Pattern: Missing use of single-line condition

Issue: -

## Description

Enforces conditions of `if`, `elseif`, `while` and `do-while` to be on a single line.

Rule provides the following settings:

* `maxLineLength`: specifies max allowed line length. If condition (and the rest of the line) would fit on it, it's enforced. Use 0 value to enforce for all conditions, regardless of length.
* `alwaysForSimpleConditions`: allows to enforce single line for all simple conditions (i.e no `&&`, `||` or `xor`), regardless of length.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.ControlStructures.RequireSingleLineCondition](https://github.com/slevomat/coding-standard/blob/master/doc/control-structures.md#slevomatcodingstandardcontrolstructuresrequiresinglelinecondition-)