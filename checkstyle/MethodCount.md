Pattern: Too many methods

Issue: -

## Description

Checks the number of methods declared in each type. This includes the number of each scope (`private`, `package`, `protected` and `public`) as well as an overall total. 

## Examples

To configure the check with defaults: 


```xml
<module name="MethodCount"/>
```
        

To configure the check to allow at most 30 methods per type: 


```xml
<module name="MethodCount">
      <property name="maxTotal" value="30"/>
</module>
```

## Further Reading

* [checkstyle - MethodCount](https://checkstyle.sourceforge.io/checks/sizes/methodcount.html#MethodCount)
