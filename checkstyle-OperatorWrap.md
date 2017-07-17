Pattern: Incorrect line wrapping for operators

Issue: -

## Description

Checks the policy on how to wrap lines on operators. 

## Examples

To configure the check: 
    
    
    <module name="OperatorWrap"/>
            

To configure the check for the assignment operator, `=`, at the end of a line: 
    
    
    <module name="OperatorWrap">
        <property name="tokens" value="ASSIGN"/>
        <property name="option" value="eol"/>
    </module>

## Further Reading

* [checkstyle - OperatorWrap](http://checkstyle.sourceforge.net/config_whitespace.html#OperatorWrap)