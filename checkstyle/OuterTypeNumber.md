Pattern: Too many defined types at the `outer` level

Issue: -

## Description

Checks for the number of types declared at the _outer_ (or _root_) level in a file. 

Rationale: It is considered good practice to only define one outer type per file. 

## Examples

To configure the check to accept 1 outer type per file: 


```xml
<module name="OuterTypeNumber"/>
```
        

To configure the check to accept 2 outer types per file: 


```xml
<module name="OuterTypeNumber">
      <property name="max" value="2"/>
</module>
```

## Further Reading

* [checkstyle - OuterTypeNumber](https://checkstyle.sourceforge.io/checks/sizes/outertypenumber.html#OuterTypeNumber)
