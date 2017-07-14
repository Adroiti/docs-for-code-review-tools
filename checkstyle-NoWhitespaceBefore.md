Pattern: Check that there is no whitespace before a token

Issue: -

## Description

Checks that there is no whitespace before a token. More specifically, it checks that it is not preceded with whitespace, or (if linebreaks are allowed) all characters on the line before are whitespace. To allow linebreaks before a token, set property `allowLineBreaks` to ` true`. 

## Examples

To configure the check: 
    
    
    <module name="NoWhitespaceBefore"/>
            

To configure the check to allow linebreaks before a DOT token: 
    
    
    <module name="NoWhitespaceBefore">
        <property name="tokens" value="DOT"/>
        <property name="allowLineBreaks" value="true"/>
    </module>

## Further Reading

* [checkstyle - NoWhitespaceBefore](http://checkstyle.sourceforge.net/config_whitespace.html#NoWhitespaceBefore)