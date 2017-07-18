Pattern: Invalid package name

Issue: -

## Description

Validates identifiers for packages. 

## Examples

The default value of `format` for module `PackageName` has been chosen to match the requirements in the [Java Language specification](http://docs.oracle.com/javase/specs/jls/se8/html/jls-6.html#jls-6.5.3) and the Sun coding conventions. However both underscores and uppercase letters are rather uncommon, so most configurations should probably assign value `^[a-z]+(\\.[a-z][a-z0-9]*)*$` to `format` for module `PackageName`, as in 


```xml
<module name="PackageName">
    <property name="format"
 value="^[a-z]+(\.[a-z][a-z0-9]*)*$"/>
</module>
```

## Further Reading

* [checkstyle - PackageName](http://checkstyle.sourceforge.net/config_naming.html#PackageName)
