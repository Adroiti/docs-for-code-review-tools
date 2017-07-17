Pattern: Uncommented `main()` method

Issue: -

## Description

Checks for uncommented `main()` methods. 

Rationale: A `main()` method is often used for debugging purposes. When debugging is finished, developers often forget to remove the method, which changes the API and increases the size of the resulting class or JAR file. With the exception of the real program entry points, all `main()` methods should be removed or commented out of the sources. 

## Examples

To configure the check: 
    
    
    <module name="UncommentedMain"/>
            

To configure the check to allow the `main` method for all classes with "Main" name: 
    
    
    <module name="UncommentedMain">
        <property name="excludedClasses" value="\.Main$"/>
    </module>

## Further Reading

* [checkstyle - UncommentedMain](http://checkstyle.sourceforge.net/config_misc.html#UncommentedMain)