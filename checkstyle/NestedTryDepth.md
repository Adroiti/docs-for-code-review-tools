Pattern: Too many nested `try-catch-finally` blocks

Issue: -

## Description

Restricts nested try blocks to a specified depth (default = 1). 

## Examples

To configure the check: 


```xml
<module name="NestedTryDepth"/>
```
        

To configure the check to allow nesting depth 3: 


```xml
<module name="NestedTryDepth">
    <property name="max" value="3"/>
</module>
```

## Further Reading

* [checkstyle - NestedTryDepth](https://checkstyle.sourceforge.io/checks/coding/nestedtrydepth.html#NestedTryDepth)
