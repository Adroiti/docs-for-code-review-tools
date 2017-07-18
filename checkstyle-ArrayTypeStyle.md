Pattern: Illegal position for array brackets

Issue: -

## Description

This rule enforces the use of either C-style or Java-style for array declarations. The default is Java-style based on Google Java Style Guide: The square brackets form a part of the _type_, not the variable: `String[] args`, not `String args[]`.

## Examples

To configure the check to enforce Java style: 


```xml
<module name="ArrayTypeStyle"/>
```
        

To configure the check to enforce C style: 


```xml
<module name="ArrayTypeStyle">
    <property name="javaStyle" value="false"/>
</module>
```

## Further Reading

* [Google Java Style Guide - Arrays](https://google.github.io/styleguide/javaguide.html#s4.1-braces)
* [checkstyle - ArrayTypeStyle](http://checkstyle.sourceforge.net/config_misc.html#ArrayTypeStyle)
