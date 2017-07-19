Pattern: Illegal token text

Issue: -

## Description

Checks specified tokens text for matching an illegal pattern from `format` property.

Default configuration:

```xml
<module name="IllegalTokenText">
    <property name="tokens" value="STRING_LITERAL, CHAR_LITERAL"/>
    <property name="format" value="\\u00(09|0(a|A)|0(c|C)|0(d|D)|22|27|5(C|c))|\\(0(10|11|12|14|15|42|47)|134)"/>
    <property name="message" value="Consider using special escape sequence instead of octal value or Unicode escaped value."/>
</module>
```

To configure the check to forbid String literals containing `"a href"`:

```xml
<module name="IllegalTokenText">
    <property name="tokens" value="STRING_LITERAL"/>
    <property name="format" value="a href"/>
</module>
```

## Further Reading

* [checkstyle - IllegalTokenText](http://checkstyle.sourceforge.net/config_coding.html#IllegalTokenText)
