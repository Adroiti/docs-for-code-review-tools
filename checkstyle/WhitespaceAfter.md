Pattern: No whitespace after token

Issue: -

## Description

Checks that a token is followed by whitespace. 

## Examples

To configure the check: 


```xml
<module name="WhitespaceAfter"/>
```
        

To configure the check for whitespace only after COMMA and SEMI tokens: 


```xml
<module name="WhitespaceAfter">
    <property name="tokens" value="COMMA, SEMI"/>
</module>
```

## Further Reading

* [checkstyle - WhitespaceAfter](https://checkstyle.sourceforge.io/checks/whitespace/whitespaceafter.html#WhitespaceAfter)
