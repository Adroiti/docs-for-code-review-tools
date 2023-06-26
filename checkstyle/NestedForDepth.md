Pattern: Too many nested `for` blocks

Issue: -

## Description

Restricts nested `for` blocks to a specified depth (default = 1). 

## Examples

To configure the check: 


```xml
<module name="NestedForDepth"/>
```
        

To configure the check to allow nesting depth 3: 


```xml
<module name="NestedForDepth">
    <property name="max" value="3"/>
</module>
```

## Further Reading

* [checkstyle - NestedForDepth](https://checkstyle.sourceforge.io/checks/coding/nestedfordepth.html#NestedForDepth)
