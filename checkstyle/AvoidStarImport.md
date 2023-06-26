Pattern: Use of star import

Issue: -

## Description

Importing all classes from a package or static members from a class leads to tight coupling between packages or classes and might lead to problems when a new version of a library introduces name clashes.

In addition, by explicitly listing all imports you can tell at a glance which class you meant to use, which simply makes reading the code that much easier. Also, modern IDEs should address possible maintenance issues related to explicit imports (e.g. removing or renaming a class).

## Examples

An example how to configure the check so that star imports from packages `java.io` and `java.net` as well as static members from class from `java.lang.Math` are allowed: 

```xml
<module name="AvoidStarImport">
   <property name="excludes" value="java.io,java.net,java.lang.Math"/>
   <property name="allowClassImports" value="false"/>
   <property name="allowStaticMemberImports" value="false"/>
</module>
```

## Further Reading

* [Google Java Style Guide - No wildcard imports](https://google.github.io/styleguide/javaguide.html#s3.3.1-wildcard-imports)
* [Stack Overflow - Why is using a wild card with a Java import statement bad?](https://stackoverflow.com/questions/147454/why-is-using-a-wild-card-with-a-java-import-statement-bad)
* [checkstyle - AvoidStarImport](https://checkstyle.sourceforge.io/checks/imports/avoidstarimport.html#AvoidStarImport)
