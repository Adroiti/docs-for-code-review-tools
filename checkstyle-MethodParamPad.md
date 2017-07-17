Pattern: Malformed padding for method parameter list

Issue: -

## Description

Checks the padding between the identifier of a method definition, constructor definition, method call, or constructor invocation; and the left parenthesis of the parameter list. That is, if the identifier and left parenthesis are on the same line, checks whether a space is required immediately after the identifier or such a space is forbidden. If they are not on the same line, reports an error, unless configured to allow line breaks. To allow line breaks after the identifier, set property `allowLineBreaks` to `true`. 

## Examples

To configure the check: 
    
    
    <module name="MethodParamPad"/>
            

To configure the check to require a space after the identifier of a method definition, except if the left parenthesis occurs on a new line: 
    
    
    <module name="MethodParamPad">
        <property name="tokens" value="METHOD_DEF"/>
        <property name="option" value="space"/>
        <property name="allowLineBreaks" value="true"/>
    </module>

## Further Reading

* [checkstyle - MethodParamPad](http://checkstyle.sourceforge.net/config_whitespace.html#MethodParamPad)