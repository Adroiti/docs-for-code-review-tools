Pattern: Missing `java.lang.Override` annotation when `{@inheritDoc}` tag exists

Issue: -

## Description

Verifies that the `java.lang.Override` annotation is present when the `{@inheritDoc}` Javadoc tag is present.

## Examples

To configure the check:


```java
 <module name="MissingOverride"/>
```
        

To configure the check for the `javaFiveCompatibility` mode: 


```java
   <module name="MissingOverride">
      <property name="javaFiveCompatibility"
 value="true"/>
   </module>
```

## Further Reading

* [checkstyle - MissingOverride](https://checkstyle.sourceforge.io/checks/annotation/missingoverride.html#MissingOverride)
