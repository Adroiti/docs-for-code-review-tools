Pattern: Overly complicated boolean return statements

Issue: -

## Description

Checks for over-complicated boolean return statements. For example the following code 
    
    
    if (valid())
        return false;
    else
        return true;
            

could be written as 
    
    
    return !valid();
            

The idea for this check has been shamelessly stolen from the equivalent [PMD](http://pmd.sourceforge.net) rule. 

## Examples

To configure the check: 
    
    
    <module name="SimplifyBooleanReturn"/>

## Further Reading

* [checkstyle - SimplifyBooleanReturn](http://checkstyle.sourceforge.net/config_coding.html#SimplifyBooleanReturn)