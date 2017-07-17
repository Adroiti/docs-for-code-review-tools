Pattern: Overly complicated boolean return statement

Issue: -

## Description

Checks for over-complicated boolean return statements. For example the following code 
    
    
    if (valid())
        return false;
    else
        return true;
            

could be written as 
    
    
    return !valid();
            

## Examples

To configure the check: 
    
    
    <module name="SimplifyBooleanReturn"/>

## Further Reading

* [checkstyle - SimplifyBooleanReturn](http://checkstyle.sourceforge.net/config_coding.html#SimplifyBooleanReturn)