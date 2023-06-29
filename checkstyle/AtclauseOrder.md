Pattern: Wrong at-clause order

Issue: -

## Description

Checks the order of [Javadoc block-tags or Javadoc tags](http://docs.oracle.com/javase/8/docs/technotes/tools/windows/javadoc.html#CHDBEFIF).

## Examples

Default configuration 


```xml
<module name="AtclauseOrder">
    <property name="tagOrder" value="@author, @version, @param,
    @return, @throws, @exception, @see, @since, @serial,
    @serialField, @serialData, @deprecated"/>
    <property name="target" value="CLASS_DEF, INTERFACE_DEF, ENUM_DEF,
    METHOD_DEF, CTOR_DEF, VARIABLE_DEF"/>
</module>
```

## Further Reading

* [checkstyle - AtclauseOrder](https://checkstyle.sourceforge.io/checks/javadoc/atclauseorder.html#AtclauseOrder)
