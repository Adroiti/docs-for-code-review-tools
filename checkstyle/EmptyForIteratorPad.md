Pattern: Wrong padding of an empty `for` iterator

Issue: -

## Description

Checks the padding of an empty `for` iterator; that is whether white space is required at an empty `for` iterator, or such white space is forbidden. No check occurs if there is a line wrap at the iterator, as in 


```java
for (Iterator foo = very.long.line.iterator();
      foo.hasNext();
     )
```
        

## Examples

To configure the check: 


```xml
<module name="EmptyForIteratorPad"/>
```
        

To configure the check to require white space at an empty `for` iterator: 


```xml
<module name="EmptyForIteratorPad">
    <property name="option" value="space"/>
</module>
```

## Further Reading

* [checkstyle - EmptyForIteratorPad](http://checkstyle.sourceforge.net/config_whitespace.html#EmptyForIteratorPad)
