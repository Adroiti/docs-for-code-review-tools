Pattern: Malformed Javadoc block tag position

Issue: -

## Description

All javadoc block tags should be placed at the beginning of a line. Tags that are not placed at the beginning are treated as plain text. To recognize intentional tag placement to text area it is better to escape the `@` symbol, and all non-escaped tags should be located at the beginning of the line.

## Examples

To place a tag explicitly as text, escape the `@` symbol with HTML entity `&#64;` or place it inside `{@code }`, for example:

```java
/**
 * &#64;serial literal in {@code @serial} Javadoc tag.
 */
```

## Further Reading

* [checkstyle - JavadocParagraph](https://checkstyle.sourceforge.io/checks/javadoc/javadocblocktaglocation.html#JavadocBlockTagLocation)
