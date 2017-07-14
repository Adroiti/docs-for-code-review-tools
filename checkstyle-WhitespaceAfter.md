Pattern: Check that a token is followed by whitespace, with the exception that it does not check for whitespace after the semicolon of an empty for iterator

Issue: -

## Description

Checks that a token is followed by whitespace. 

## Examples

To configure the check: 
    
    
    <module name="WhitespaceAfter"/>
            

To configure the check for whitespace only after COMMA and SEMI tokens: 
    
    
    <module name="WhitespaceAfter">
        <property name="tokens" value="COMMA, SEMI"/>
    </module>

## Further Reading

* [checkstyle - WhitespaceAfter](http://checkstyle.sourceforge.net/config_whitespace.html#WhitespaceAfter)