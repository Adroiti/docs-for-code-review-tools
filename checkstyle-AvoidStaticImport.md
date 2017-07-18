Pattern: Use of static `import`

Issue: -

## Description

Checks that there are no static `import` statements. 

Rationale: Importing static members can lead to naming conflicts between class' members. It may lead to poor code readability since it may no longer be clear what class a member resides in (without looking at the import statement). 

## Examples

An example of how to configure the check so that the `java.lang.System.out` member and all members from `java.lang.Math` are allowed: 


```java
<module name="AvoidStaticImport">
  <property name="excludes" value="java.lang.System.out,java.lang.Math.*"/>
</module>
```

## Further Reading

* [checkstyle - AvoidStaticImport](http://checkstyle.sourceforge.net/config_imports.html#AvoidStaticImport)
