Pattern: Malformed Javadoc position

Issue: -

## Description

Checks that Javadocs are located at the correct position. Javadocs are recognized only when placed immediately before module, package, class, interface, constructor, method, or field declarations. Any other position, like in the body of a method, will be ignored by the javadoc tool and is considered invalid by this check.

## Examples

The following code produces a violation because Javadocs should be before all annotations of the Javadoc's target:

```java
@SuppressWarnings("serial")
/**
 * This comment looks like javadoc but it at an invalid location.
 * Therefore, the text will not get into TestClass.html and the check will produce a violation.
 */
public class TestClass {
}
```

## Further Reading

* [checkstyle - JavadocParagraph](https://checkstyle.sourceforge.io/config_javadoc.html#InvalidJavadocPosition)
