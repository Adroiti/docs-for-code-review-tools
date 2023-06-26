Pattern: Whitespace after token

Issue: -

## Description

Checks that there is no whitespace after a token. More specifically, it checks that it is not followed by whitespace, or (if line breaks are allowed) all characters on the line after are whitespace. To forbid line breaks after a token, set property `allowLineBreaks` to `false`. 

The check processes [ARRAY_DECLARATOR](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#ARRAY_DECLARATOR) and [INDEX_OP](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#INDEX_OP) tokens specially from other tokens. Actually it is checked that there is no whitespace before this tokens, not after them. 

## Examples

To configure the check: 


```xml
<module name="NoWhitespaceAfter"/>
```
        

To configure the check to forbid line breaks after a DOT token: 


```xml
<module name="NoWhitespaceAfter">
    <property name="tokens" value="DOT"/>
    <property name="allowLineBreaks" value="false"/>
</module>
```

## Further Reading

* [checkstyle - NoWhitespaceAfter](https://checkstyle.sourceforge.io/checks/whitespace/nowhitespaceafter.html#NoWhitespaceAfter)
