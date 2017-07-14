Pattern: Check that an overriding finalize() method invokes super.finalize()

Issue: -

## Description

Checks that an overriding `finalize()` method invokes `super.finalize()`. Does not check native methods, as they have no possible java defined implementation. 

Reference: [ Use Finalization Only When You Must](http://www.oracle.com/technetwork/java/javamail/finalization-137655.html). 

## Examples

To configure the check: 
    
    
    <module name="SuperFinalize"/>

## Further Reading

* [checkstyle - SuperFinalize](http://checkstyle.sourceforge.net/config_coding.html#SuperFinalize)