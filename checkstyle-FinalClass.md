Pattern: Class should be declared as final

Issue: -

## Description

Checks that a class which has only private constructors is declared as final. Doesn't check for classes nested in interfaces or annotations, as they are always `final` there. 

## Examples

To configure the check: 
    
    
    <module name="FinalClass"/>

## Further Reading

* [checkstyle - FinalClass](http://checkstyle.sourceforge.net/config_design.html#FinalClass)