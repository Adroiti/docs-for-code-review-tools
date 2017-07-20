Pattern: Use of Unicode escape

Issue: -

## Description

Prefer using actual Unicode character (e.g. `∞`) over the equivalent Unicode escape (e.g. `\u221e`) - this makes the code easier to read and understand. Use escapes for non-printable characters, and comment if necessary.

Never make your code less readable simply out of fear that some programs might not handle non-ASCII characters properly. If that should happen, those programs are **broken** and they must be **fixed**.

## Default configuration

```xml
<module name="AvoidEscapedUnicodeCharacters">
    <property name="allowEscapesForControlCharacters" value="true"/>
    <property name="allowByTailComment" value="true"/>
    <property name="allowNonPrintableEscapes" value="true"/>
</module>
```

## Examples

Examples of using Unicode:


```java
String unitAbbrev = "μs"; //Best: perfectly clear even without a comment.
String unitAbbrev = "\u03bcs"; //Poor: the reader has no idea what this is.
```

An example of non-printable (control) characters:

```java
return '\ufeff' + content; // byte order mark
```

An example of how to configure the check to allow using escapes for non-printable (control) characters:


```xml
<module name="AvoidEscapedUnicodeCharacters">
    <property name="allowEscapesForControlCharacters" value="true"/>
</module>
```

Example of using escapes with trail comment:


```java
String unitAbbrev = "\u03bcs"; // Greek letter mu, "s"
```

An example of how to configure the check to allow using escapes if trail comment is present: 


```xml
<module name="AvoidEscapedUnicodeCharacters">
    <property name="allowByTailComment" value="true"/>
</module>
```

Example of using escapes if literal contains only them: 


```java
String unitAbbrev = "\u03bc\u03bc\u03bc";
```

An example of how to configure the check to allow escapes if literal contains only them: 


```xml
<module name="AvoidEscapedUnicodeCharacters">
    <property name="allowIfAllCharactersEscaped" value="true"/>
</module>
```

An example of how to configure the check to allow non-printable escapes: 


```xml
<module name="AvoidEscapedUnicodeCharacters">
    <property name="allowNonPrintableEscapes" value="true"/>
</module>
```

## Further Reading

* [Google Java Style Guide - Non-ASCII characters](https://google.github.io/styleguide/javaguide.html#s2.3.3-non-ascii-characters)
* [checkstyle - AvoidEscapedUnicodeCharacters](http://checkstyle.sourceforge.net/config_misc.html#AvoidEscapedUnicodeCharacters)
