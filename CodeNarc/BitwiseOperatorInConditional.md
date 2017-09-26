Pattern: Bitwise operator in conditional

Issue: -

## Description

Checks for bitwise operations in conditionals. For instance, the condition `if (a | b)` is almost always a mistake and should be `if (a || b)`. If you need to do a bitwise operation then it is best practice to extract a temp variable.

Example of violations:

``` groovy
if (a | b) { }
if (a & b) { }
```

## Further Reading

* [CodeNarc - BitwiseOperatorInConditional](http://codenarc.sourceforge.net/codenarc-rules-basic.html#BitwiseOperatorInConditional)