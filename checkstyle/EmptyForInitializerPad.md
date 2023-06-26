Pattern: Wrong padding of an empty `for` initializer

Issue: -

## Description

Checks the padding of an empty `for` initializer; that is whether white space is required at an empty `for` initializer, or such white space is forbidden. No check occurs if there is a line wrap at the initializer, as in 


```java
for (
      ; i < j; i++, j--)
```
        

## Examples

To configure the check: 


```xml
<module name="EmptyForInitializerPad"/>
```
        

To configure the check to require white space at an empty `for` iterator: 


```xml
<module name="EmptyForInitializerPad">
    <property name="option" value="space"/>
</module>
```

## Further Reading

* [checkstyle - EmptyForInitializerPad](https://checkstyle.sourceforge.io/checks/whitespace/emptyforinitializerpad.html#EmptyForInitializerPad)
