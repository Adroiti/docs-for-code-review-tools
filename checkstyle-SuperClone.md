Pattern: Check that an overriding clone() method invokes super.clone()

Issue: -

## Description

Checks that an overriding `clone()` method invokes `super.clone()`. Does not check native methods, as they have no possible java defined implementation. 

Reference: [Object.clone()](https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html#clone%28%29). 

## Examples

To configure the check: 
    
    
    <module name="SuperClone"/>

## Further Reading

* [checkstyle - SuperClone](http://checkstyle.sourceforge.net/config_coding.html#SuperClone)