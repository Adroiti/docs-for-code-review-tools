Pattern: Illegal token text

Issue: -

## Description

Checks specified tokens text for matching an illegal pattern from `format` property.

By default Google Java Style Guide is applied: For any character that has a special escape sequence, that sequence should be used rather than the corresponding octal (e.g. `\012`) or Unicode (e.g. `\u000a`) escape.

## Default configuration

```xml
<module name="IllegalTokenText">
    <property name="tokens" value="STRING_LITERAL, CHAR_LITERAL"/>
    <property name="format" value="\\u00(09|0(a|A)|0(c|C)|0(d|D)|22|27|5(C|c))|\\(0(10|11|12|14|15|42|47)|134)"/>
    <property name="message" value="Consider using special escape sequence instead of octal value or Unicode escaped value."/>
</module>
```

## Examples

Example of **incorrect** code:

```python
string newLine = "\015\012";
```

Example of **correct** code:

```python
string newLine = "\r\n";
```

To configure the check to forbid String literals containing `"a href"`:

```xml
<module name="IllegalTokenText">
    <property name="tokens" value="STRING_LITERAL"/>
    <property name="format" value="a href"/>
</module>
```

## Further Reading

* [Google Java Style Guide - Special escape sequences](https://google.github.io/styleguide/javaguide.html#s2.1-file-name)
* [checkstyle - IllegalTokenText](https://checkstyle.sourceforge.io/checks/coding/illegaltokentext.html#IllegalTokenText)
