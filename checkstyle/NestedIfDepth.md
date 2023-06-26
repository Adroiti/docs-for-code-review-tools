Pattern: Too many nested `if-else` blocks

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

* [checkstyle - NestedIfDepth](https://checkstyle.sourceforge.io/checks/coding/nestedifdepth.html#NestedIfDepth)
