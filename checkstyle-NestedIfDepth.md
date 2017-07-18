Pattern: Restrict nested `if-else` block to a specified depth

Issue: -

## Description

Restricts nested `if-else` blocks to a specified depth (default = 1). 

## Examples

To configure the check: 


```xml
<module name="NestedIfDepth"/>
```
        

To configure the check to allow nesting depth 3: 


```xml
<module name="NestedIfDepth">
    <property name="max" value="3"/>
</module>
```

## Further Reading

* [checkstyle - NestedIfDepth](http://checkstyle.sourceforge.net/config_coding.html#NestedIfDepth)
