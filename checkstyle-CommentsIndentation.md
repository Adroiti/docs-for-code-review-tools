Pattern: Malformed comment indentation

Issue: -

## Description

This rule controls the indentation between comments and surrounding code. By default it enforces recommendation by Google Java Style Guide - comments should be indented at the same level as the surrounding code.

**Note**: if comment block _appears_ to be at the same level as surrounding code it's most likely caused by usage of mixed spaces and tabs.

## Default configuration

```xml
<module name="CommentsIndentation"/>
```

## Examples

Example of **incorrect** code:

```java
// comment at the same identation level
boolean bool = true;

  /* violation
  * (block comment should have the same indentation level as line below)
  */
double d = 3.14;
```

Example of **correct** code:

```java
// comment at the same identation level
boolean bool = true;

/* Block comment
*  at the same indentation level
*/
double d = 3.14;
```

## Further Reading

* [Google Java Style Guide - Block comment style](http://checkstyle.sourceforge.net/reports/google-java-style-20170228.html#s4.8.6.1-block-comment-style)
* [checkstyle - CommentsIndentation](http://checkstyle.sourceforge.net/config_misc.html#CommentsIndentation)
