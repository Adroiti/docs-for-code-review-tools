Pattern: Long lines

Issue: -

## Description

Checks for long lines. 

Rationale: Long lines are hard to read in printouts or if developers have limited screen space for the source code, e.g. if the IDE displays additional information like project tree, class hierarchy, etc. 

## Examples

To configure the check to accept lines up to 120 characters long: 
    
    
    <module name="LineLength">
        <property name="max" value="120"/>
    </module>
            

To configure the check to ignore lines that begin with " * ", followed by just one word, such as within a Javadoc comment: 
    
    
    <module name="LineLength">
       <property name="ignorePattern" value="^ *\* *[^ ]+$"/>
    </module>

## Further Reading

* [checkstyle - LineLength](http://checkstyle.sourceforge.net/config_sizes.html#LineLength)