Pattern: Inconsistent type cast

Issue: -

## Description

Enforces using shorthand cast operators, forbids use of unset and binary cast operators: `(bool)` instead of `(boolean)`, `(int)` instead of `(integer)`, `(float)` instead of `(double)` or `(real)`. `(binary)` and `(unset)` are forbidden.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.PHP.TypeCast](https://github.com/slevomat/coding-standard/blob/master/doc/php.md#slevomatcodingstandardphptypecast-)