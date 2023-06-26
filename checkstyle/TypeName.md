Pattern: Invalid type name

Issue: -

## Description

Validates identifiers for classes, interfaces, enums, and annotations. 

## Examples

The following configuration element ensures that interface names begin with `"I_"`, followed by letters and digits: 


```xml
<module name="TypeName">
    <property name="format" value="^I_[a-zA-Z0-9]*$"/>
    <property name="tokens" value="INTERFACE_DEF"/>
</module>
```

## Further Reading

* [checkstyle - TypeName](https://checkstyle.sourceforge.io/checks/naming/typename.html#TypeName)
