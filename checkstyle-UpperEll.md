Pattern: Prefer `L` over `l` for long constant names

Issue: -

## Description

Checks that long constants are defined with an upper ell. That is `'L'` and not `'l'`. This is in accordance with the Java Language Specification, [Section 3.10.1](http://docs.oracle.com/javase/specs/jls/se8/html/jls-3.html#jls-3.10.1). 

The capital `L` looks a lot like `1`. 

## Examples

To configure the check: 
    
    
    <module name="UpperEll"/>

## Further Reading

* [checkstyle - UpperEll](http://checkstyle.sourceforge.net/config_misc.html#UpperEll)