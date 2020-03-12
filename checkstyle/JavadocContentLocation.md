Pattern: Malformed Javadoc content location

Issue: -

## Description

Checks that the Javadoc content begins from the same position for all Javadoc comments in the project. Any leading asterisks and spaces are not counted as the beginning of the content and are therefore ignored.

It is possible to enforce two different styles:

* {@code first_line} - Javadoc content starts from the first line:
```java
/** Summary text.
  * More details.
  */
public void method();
```

* {@code second_line} - Javadoc content starts from the second line:
```java
/**
  * Summary text.
  * More details.
  */
public void method();
```

## Examples

By default Check validate that the Javadoc content starts from the second line:
```xml
<module name="JavadocContentLocationCheck"/>
```

This setting produces a violation for each multi-line comment starting on the same line as the initial asterisks:

```java
/** This comment causes a violation because it starts from the first line
  * and spans several lines.
  */
/**
  * This comment is OK because it starts from the second line.
  */
/** This comment is OK because it is on the single line. */
```

To ensure that Javadoc content starts from the first line:

```xml
<module name="JavadocContentLocationCheck">
  <property name="location" value="first_line"/>
</module>
```

This setting produces a violation for each comment not starting on the same line as the initial asterisks:
```java
/** This comment is OK because it starts on the first line.
   * There may be additional text.
   */
/**
  * This comment causes a violation because it starts on the second line.
  */
/** This single-line comment also is OK. */
```

## Further Reading

* [checkstyle - JavadocContentLocation](http://checkstyle.sourceforge.net/config_javadoc.html#JavadocContentLocation)