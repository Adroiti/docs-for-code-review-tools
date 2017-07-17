Pattern: Wrong padding of parentheses for typecast

Issue: -

## Description

Checks the policy on the padding of parentheses for typecasts. That is, whether a space is required after a left parenthesis and before a right parenthesis, or such spaces are forbidden. 

## Examples

To configure the check: 
    
    
    <module name="TypecastParenPad"/>
            

To configure the check to require spaces: 
    
    
    <module name="TypecastParenPad">
        <property name="option" value="space"/>
    </module>

## Further Reading

* [checkstyle - TypecastParenPad](http://checkstyle.sourceforge.net/config_whitespace.html#TypecastParenPad)