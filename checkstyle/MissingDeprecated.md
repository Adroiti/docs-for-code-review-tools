Pattern: Missing `java.lang.Deprecated` annotation and/or `@deprecated` tag

Issue: -

## Description

Verifies that both the `java.lang.Deprecated` annotation is present and the `@deprecated` Javadoc tag is present when either is present.

## Examples

To configure the check:


```xml
<module name="MissingDeprecated"/>
```
        

In addition you can configure this check with skipNoJavadoc option: 


```xml
<module name="MissingDeprecated">
    <property name="skipNoJavadoc" value="true" />
</module>
```
        

Examples of validating source code with skipNoJavadoc:


```java
@deprecated
public static final int MY_CONST = 123456; // no violation
 

/** This Javadoc is missing deprecated tag. */
@deprecated
public static final int COUNTER = 10; // violation as Javadoc exists
```

## Further Reading

* [checkstyle - MissingDeprecated](http://checkstyle.sourceforge.net/config_annotation.html#MissingDeprecated)
