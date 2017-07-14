Pattern: Check that there is a newline at the end of each file

Issue: -

## Description

Checks whether files end with a line separator. 

Rationale: Any source files and text files in general should end with a line separator to let other easily add new content at the end of file and "diff" command does not show previous lines as changed.   
Example (line 36 should not be in diff): 

Old Rationale: CVS source control management systems will even print a warning when it encounters a file that doesn't end with a line separator. 

Attention: property fileExtensions works with files that are passed by similar property for at [Checker](config.html#Checker). Please make sure required file extensions are mentioned at Checker's fileExtensions property. 

## Examples

To configure the check: 
    
    
    <module name="NewlineAtEndOfFile"/>
            

To configure the check to always use Unix-style line separators: 
    
    
    <module name="NewlineAtEndOfFile">
        <property name="lineSeparator" value="lf"/>
    </module>
            

To configure the check to work only on Java, XML and Python files: 
    
    
    <module name="NewlineAtEndOfFile">
        <property name="fileExtensions" value="java, xml, py"/>
    </module>

## Further Reading

* [checkstyle - NewlineAtEndOfFile](http://checkstyle.sourceforge.net/config_misc.html#NewlineAtEndOfFile)