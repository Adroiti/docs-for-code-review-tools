Pattern: Mixing different binary boolean operators

Issue: -

## Description

Forbids mixing different binary boolean operators within a single expression without making precedence clear using parentheses.

## Example

Example of **incorrect** code:

``` php
if (true && true || true);
```
  
Example of **correct** code:

``` php
if ((true && true) || true);
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.RequireExplicitBooleanOperatorPrecedenceSniff ](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/RequireExplicitBooleanOperatorPrecedenceSniff.php)