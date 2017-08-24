Pattern: Whitespace before a token

Issue: -

## Description

Checks that there is no whitespace before a token. More specifically, it checks that it is not preceded with whitespace, or (if line breaks are allowed) all characters on the line before are whitespace. To allow line breaks before a token, set property `allowLineBreaks` to `true`. 

## Examples

To configure the check: 


```xml
<module name="NoWhitespaceBefore"/>
```
        

To configure the check to allow line breaks before a DOT token: 


```xml
<module name="NoWhitespaceBefore">
    <property name="tokens" value="DOT"/>
    <property name="allowLineBreaks" value="true"/>
</module>
```

## Further Reading

* [checkstyle - NoWhitespaceBefore](http://checkstyle.sourceforge.net/config_whitespace.html#NoWhitespaceBefore)
