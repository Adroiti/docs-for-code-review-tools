Pattern: Invalid parameter name

Issue: -

## Description

Checks that method and `catch` parameter names conform to a format specified by the `format` property. By using `accessModifiers` property it is possible to specify different formats for methods at different visibility levels. 

## Examples

To configure the check: 


```xml
<module name="ParameterName"/>
```
        

An example of how to configure the check to skip methods with Override annotation from validation: 


```xml
<module name="ParameterName">
    <property name="ignoreOverridden" value="true"/>
</module>
```
 

An example of how to configure the check for names that begin with a lower case letter, followed by letters and digits is: 


```xml
<module name="ParameterName">
    <property name="format" value="^[a-z][a-zA-Z0-9]+$"/>
</module>
```
        

The following configuration checks that the parameters always start with two lowercase characters and, in addition, that public method parameters cannot be one character long: 


```xml
<module name="ParameterName">
  <property name="format" value="^[a-z]([a-z0-9][a-zA-Z0-9]*)?$"/>
  <property name="accessModifiers" value="protected, package, private"/>
  <message key="name.invalidPattern" value="Parameter name ''{0}'' must match pattern ''{1}''"/>
</module>
<module name="ParameterName">
<property name="format" value="^[a-z][a-z0-9][a-zA-Z0-9]*$"/>
    <property name="accessModifiers" value="public"/>
    <message key="name.invalidPattern" value="Parameter name ''{0}'' must match pattern ''{1}''"/>
</module>
```

## Further Reading

* [checkstyle - ParameterName](http://checkstyle.sourceforge.net/config_naming.html#ParameterName)
