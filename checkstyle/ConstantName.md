Pattern: Invalid constant name

Issue: -

## Description

Validates identifiers for constants (`static`, ` final` fields). 

## Examples

Property `format` in module `ConstantName` is used to specify names to be allowed. The following configuration apart from names allowed by default allows `log` or `logger`: 


```xml
<module name="ConstantName">
    <property name="format"
 value="^log(ger)?|[A-Z][A-Z0-9]*(_[A-Z0-9]+)*$"/>
</module>
```

## Further Reading

* [checkstyle - ConstantName](https://checkstyle.sourceforge.io/checks/naming/constantname.html#ConstantName)
