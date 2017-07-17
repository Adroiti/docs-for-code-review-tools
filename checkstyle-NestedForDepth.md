Pattern: Restrict nested `for` block to a specified depth

Issue: -

## Description

Restricts nested `for` blocks to a specified depth (default = 1). 

## Examples

To configure the check: 
    
    
    <module name="NestedForDepth"/>
            

To configure the check to allow nesting depth 3: 
    
    
    <module name="NestedForDepth">
        <property name="max" value="3"/>
    </module>

## Further Reading

* [checkstyle - NestedForDepth](http://checkstyle.sourceforge.net/config_coding.html#NestedForDepth)