Pattern: Missing whitespace after asterisk

Issue: -

## Description

Checks that there is at least one whitespace after the leading asterisk. Although spaces after asterisks are optional in the Javadoc comments, their absence makes the documentation difficult to read. It is the de facto standard to put at least one whitespace after the leading asterisk.

## Examples

```java
/** This is valid single-line Javadoc. */
class TestClass {
  /**
   *This is invalid Javadoc.
   */
  int invalidJavaDoc;
  /**
   * This is valid Javadoc.
   */
  void validJavaDocMethod() {
  }
  /**This is invalid single-line Javadoc. */
  void invalidSingleLineJavaDocMethod() {
  }
  /** This is valid single-line Javadoc. */
  void validSingleLineJavaDocMethod() {
  }
}
    
```

## Further Reading

* [checkstyle - JavadocMissingWhitespaceAfterAsterisk](https://checkstyle.sourceforge.io/config_javadoc.html#JavadocMissingWhitespaceAfterAsterisk)
