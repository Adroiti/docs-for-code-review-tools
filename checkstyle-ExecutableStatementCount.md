Pattern: Too many executable statements

Issue: -

## Description

Restricts the number of executable statements to a specified limit. 

## Examples

To configure the check: 


```xml
<module name="ExecutableStatementCount"/>
```
        

To configure the check with a threshold of 20 for constructor and method definitions: 


```xml
<module name="ExecutableStatementCount">
    <property name="max" value="20"/>
    <property name="tokens" value="CTOR_DEF,METHOD_DEF"/>
</module>
```

## Further Reading

* [checkstyle - ExecutableStatementCount](http://checkstyle.sourceforge.net/config_sizes.html#ExecutableStatementCount)
