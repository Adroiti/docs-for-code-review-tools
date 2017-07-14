Pattern: Check that classes (except abstract one) define a ctor and don't rely on the default one

Issue: -

## Description

Checks that classes (except abstract ones) define a constructor and don't rely on the default one. 

## Examples

To configure the check: 
    
    
    <module name="MissingCtor"/>

## Further Reading

* [checkstyle - MissingCtor](http://checkstyle.sourceforge.net/config_coding.html#MissingCtor)