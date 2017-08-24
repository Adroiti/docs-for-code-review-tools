Pattern: File does not end with a newline

Issue: -

## Description

Checks whether files end with a line separator. 

Rationale: Any source files and text files in general should end with a line separator to let others easily add new content at the end of file.

Old Rationale: CVS source control management systems will even print a warning when it encounters a file that doesn't end with a line separator. 

Attention: property `fileExtensions` works with files that are passed by similar property for at [Checker](http://checkstyle.sourceforge.net/config.html#Checker). Please make sure required file extensions are mentioned at Checker's `fileExtensions` property. 

## Examples

To configure the check: 


```xml
<module name="NewlineAtEndOfFile"/>
```
        

To configure the check to always use Unix-style line separators: 


```xml
<module name="NewlineAtEndOfFile">
    <property name="lineSeparator" value="lf"/>
</module>
```
        

To configure the check to work only on Java, XML and Python files: 


```xml
<module name="NewlineAtEndOfFile">
    <property name="fileExtensions" value="java, xml, py"/>
</module>
```

## Further Reading

* [checkstyle - NewlineAtEndOfFile](http://checkstyle.sourceforge.net/config_misc.html#NewlineAtEndOfFile)
