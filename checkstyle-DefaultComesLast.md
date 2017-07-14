Pattern: Check that the default is after all the cases in a switch statement.

Issue: -

## Description

Check that the `default` is after all the `case`s in a `switch` statement. 

Rationale: Java allows `default` anywhere within the `switch` statement. But it is more readable if it comes after the last `case`. 

## Examples

To configure the check: 
    
    
    <module name="DefaultComesLast"/>
            

To configure the check for skipIfLastAndSharedWithCase: 
    
    
    <module name="DefaultComesLast">
        <property name="skipIfLastAndSharedWithCase" value="true"/>
    </module>
            

Example when skipIfLastAndSharedWithCase is set to true. 
    
    
    switch (i) {
        case 1:
            break;
        case 2:
        default: // No violation with the new option is expected
            break;
        case 3:
            break;
    }
    switch (i) {
        case 1:
            break;
        default: // violation with the new option is expected
        case 2:
            break;
    }

## Further Reading

* [checkstyle - DefaultComesLast](http://checkstyle.sourceforge.net/config_coding.html#DefaultComesLast)