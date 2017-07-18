Pattern: Illegal token text

Issue: -

## Description

Checks specified tokens text for matching an illegal pattern from `format` property. By default no tokens are specified. 

## Examples

To configure the check to forbid String literals containing `"a href"`:


```xml
<module name="IllegalTokenText">
    <property name="tokens" value="STRING_LITERAL"/>
    <property name="format" value="a href"/>
</module>
```

To configure the check to forbid leading zeros in an integer literal, other than zero and a hex literal:


```xml
<module name="IllegalTokenText">
    <property name="tokens" value="NUM_INT,NUM_LONG"/>
    <property name="format" value="^0[^lx]"/>
    <property name="ignoreCase" value="true"/>
</module>

## Further Reading

* [checkstyle - IllegalTokenText](http://checkstyle.sourceforge.net/config_coding.html#IllegalTokenText)
