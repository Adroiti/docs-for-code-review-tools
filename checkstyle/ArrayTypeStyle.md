Pattern: Illegal position for array brackets

Issue: -

## Description

This rule enforces the use of either C-style or Java-style for array declarations. The default is Java-style based on Google Java Style Guide - the square brackets form a part of the _type_, not the variable: `String[] args`, not `String args[]`.

## Default configuration

```xml
<module name="ArrayTypeStyle"/>
```

## Examples

To configure the check to enforce C style: 

```xml
<module name="ArrayTypeStyle">
    <property name="javaStyle" value="false"/>
</module>
```

## Further Reading

* [Google Java Style Guide - Arrays](https://google.github.io/styleguide/javaguide.html#s4.8.3-arrays)
* [checkstyle - ArrayTypeStyle](https://checkstyle.sourceforge.io/checks/misc/arraytypestyle/arraytypestyle.html#ArrayTypeStyle)
