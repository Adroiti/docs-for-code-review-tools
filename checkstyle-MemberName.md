Pattern: Invalid instance variable name

Issue: -

## Description

Validates identifiers for non-`static` fields. 

## Examples

This is an example of a configuration of the `MemberName` module to ensure that member identifiers begin with `'m'`, followed by an upper case letter, and then letters and digits: 


```xml
<module name="MemberName">
  <property name="format" value="^m[A-Z][a-zA-Z0-9]*$"/>
</module>
```

## Further Reading

* [checkstyle - MemberName](http://checkstyle.sourceforge.net/config_naming.html#MemberName)
