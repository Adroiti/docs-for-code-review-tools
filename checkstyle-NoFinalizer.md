Pattern: Check that no method having zero parameters is defined using the name finalize

Issue: -

## Description

Verifies there are no `finalize()` methods defined in a class. 

## Examples

To configure the check: 
    
    
    <module name="NoFinalizer"/>

## Further Reading

* [checkstyle - NoFinalizer](http://checkstyle.sourceforge.net/config_coding.html#NoFinalizer)