Pattern: Prefer `L` over `l` for long constant names

Issue: -

## Description

Checks that long constants are defined with capitalized `'l'`. This is in accordance with the Java Language Specification, [Section 3.10.1](http://docs.oracle.com/javase/specs/jls/se8/html/jls-3.html#jls-3.10.1). 

The suffix `L` is preferred, because the letter `l` (ell) is often hard to distinguish from the digit `1` (one).

## Examples

To configure the check: 


```xml
<module name="UpperEll"/>
```

## Further Reading

* [checkstyle - UpperEll](http://checkstyle.sourceforge.net/config_misc.html#UpperEll)
