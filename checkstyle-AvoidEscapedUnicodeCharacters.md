Pattern: Use of Unicode escape

Issue: -

## Description

Prefer using actual Unicode character (e.g. `∞`) over the equivalent Unicode escape (e.g. `\u221e`) - this makes the code easier to read and understand. Use escapes for non-printable characters, and comment if necessary.

You should not make code less readable simply out of fear that some programs might not handle non-ASCII characters properly. If that should happen, those programs are **broken** and they must be **fixed**.

## Default configuration

```xml
<module name="AvoidEscapedUnicodeCharacters">
    <property name="allowEscapesForControlCharacters" value="true"/>
    <property name="allowByTailComment" value="true"/>
    <property name="allowNonPrintableEscapes" value="true"/>
</module>
```

- `allowEscapesForControlCharacters`: Allow use escapes for non-printable(control) characters;
- `allowByTailComment`: Allow use escapes if trail comment is present.
- `allowIfAllCharactersEscaped`: Allow if all characters in literal are escaped.
- `allowNonPrintableEscapes`: Allow if all characters in literal are escaped.

## Examples

Example of **incorrect** code:

```java
String unitAbbrev = "μs"; //Best: perfectly clear even without a comment.
```

Example of **correct** code:

```java
//Poor: the reader has no idea what this is.
String unitAbbrev = "\u03bcs";
```

## Further Reading

* [Google Java Style Guide - Non-ASCII characters](https://google.github.io/styleguide/javaguide.html#s2.3.3-non-ascii-characters)
* [checkstyle - AvoidEscapedUnicodeCharacters](http://checkstyle.sourceforge.net/config_misc.html#AvoidEscapedUnicodeCharacters)
