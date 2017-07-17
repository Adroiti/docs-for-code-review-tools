Pattern: Variable declaration is distanced from it's first usage

Issue: -

## Description

Checks the distance between declaration of variable and its first usage. 

## Examples

Example #1: 
    
    
    int count;
    a = a + b;
    b = a + a;
    count = b; // DECLARATION OF VARIABLE 'count'
               // SHOULD BE HERE (distance = 3)
            

Example #2: 
    
    
    int count;
    {
         a = a + b;
         count = b; // DECLARATION OF VARIABLE 'count'
                    // SHOULD BE HERE (distance = 2)
    }
            

Check can detect a block of initialization methods. If a variable is used in such a block and there is no other statements after this variable then distance=1. 

Case #1: 
    
    
    int minutes = 5;
    Calendar cal = Calendar.getInstance();
    cal.setTimeInMillis(timeNow);
    cal.set(Calendar.SECOND, 0);
    cal.set(Calendar.MILLISECOND, 0);
    cal.set(Calendar.HOUR_OF_DAY, hh);
    cal.set(Calendar.MINUTE, minutes);
            

The distance for the variable minutes is 1 even though this variable is used in the fifth method's call. 

Case #2: 
    
    
    int minutes = 5;
    Calendar cal = Calendar.getInstance();
    cal.setTimeInMillis(timeNow);
    cal.set(Calendar.SECOND, 0);
    cal.set(Calendar.MILLISECOND, 0);
    System.out.println(cal);
    cal.set(Calendar.HOUR_OF_DAY, hh);
    cal.set(Calendar.MINUTE, minutes);
             

The distance for the variable minutes is 6 because there is one more expression (except the initialization block) between the declaration of this variable and its usage. 

An example how to configure this Check: 
    
    
    <module name="VariableDeclarationUsageDistance"/>
             

An example of how to configure this Check: \- to set the allowed distance to 4; \- to ignore variables with prefix '^temp'; \- to force the validation between scopes; \- to check the final variables; 
    
    
    <module name="VariableDeclarationUsageDistance">
        <property name="allowedDistance" value="4"/>
        <property name="ignoreVariablePattern" value="^temp.*"/>
        <property name="validateBetweenScopes" value="true"/>
        <property name="ignoreFinal" value="false"/>
    </module>

## Further Reading

* [checkstyle - VariableDeclarationUsageDistance](http://checkstyle.sourceforge.net/config_coding.html#VariableDeclarationUsageDistance)