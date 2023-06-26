Pattern: Invalid `abstract` class name

Issue: -

## Description

Validates identifiers for `abstract` classes.

## Examples

The following example shows how to configure the `AbstractClassName` to checks names, but ignore missing `abstract` modifiers: 


```xml
<module name="AbstractClassName">
  <property name="ignoreModifier" value="true"/>
</module>
```

## Further Reading

* [checkstyle - AbstractClassName](https://checkstyle.sourceforge.io/checks/naming/abstractclassname/abstractclassname.html#AbstractClassName)
