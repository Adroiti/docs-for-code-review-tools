Pattern: Restrict nested try-catch-finally blocks to a specified depth

Issue: -

## Description

Restricts nested try blocks to a specified depth (default = 1). 

## Examples

To configure the check: 
    
    
    <module name="NestedTryDepth"/>
            

To configure the check to allow nesting depth 3: 
    
    
    <module name="NestedTryDepth">
        <property name="max" value="3"/>
    </module>

## Further Reading

* [checkstyle - NestedTryDepth](http://checkstyle.sourceforge.net/config_coding.html#NestedTryDepth)