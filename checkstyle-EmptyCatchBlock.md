Pattern: Use of empty `catch` block

Issue: -

## Description

Checks for empty `catch` blocks. There are two options to make validation more precise (by default check allows empty `catch` block with any comment inside): 

## Examples

To configure the check to suppress empty `catch` block if exception's variable name is `expected` or `ignore` or there's any comment inside: 
    
    
    <module name="EmptyCatchBlock">
        <property name="exceptionVariableName" value="expected|ignore"/>
    </module>
            

To configure the check to suppress empty `catch` block if single-line comment inside is "//This is expected": 
    
    
    <module name="EmptyCatchBlock">
        <property name="commentFormat" value="This is expected"/>
    </module>
            

To configure the check to suppress empty `catch` block if single-line comment inside is "//This is expected" or exception's variable name is "myException" (any option is matching): 
    
    
    <module name="EmptyCatchBlock">
        <property name="commentFormat" value="This is expected"/>
        <property name="exceptionVariableName" value="myException"/>
    </module>
            

Such empty blocks would be suppressed: 
    
    
    try {
        throw new RuntimeException();
    } catch (RuntimeException e) {
        //This is expected
    }
    ...
    try {
        throw new RuntimeException();
    } catch (RuntimeException e) {
        //   This is expected
    }
    ...
    try {
        throw new RuntimeException();
    } catch (RuntimeException e) {
        // This is expected
        // some another comment
    }
    ...
    try {
        throw new RuntimeException();
    } catch (RuntimeException e) {
        /* This is expected */
    }
    ...
    try {
        throw new RuntimeException();
    } catch (RuntimeException e) {
        /*
        *
        * This is expected
        * some another comment
        */
    }
    ...
    try {
        throw new RuntimeException();
    } catch (RuntimeException myException) {
    
    }

## Further Reading

* [checkstyle - EmptyCatchBlock](http://checkstyle.sourceforge.net/config_blocks.html#EmptyCatchBlock)