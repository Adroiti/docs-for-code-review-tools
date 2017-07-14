Pattern: Long anonymous inner classes

Issue: -

## Description

Checks for long anonymous inner classes. 

Rationale: If an anonymous inner class becomes very long it is hard to understand and to see the flow of the method where the class is defined. Therefore long anonymous inner classes should usually be refactored into a named inner class. See also Bloch, Effective Java, p. 93. 

## Examples

To configure the check to accept files with up to 60 lines: 
    
    
    <module name="AnonInnerLength">
          <property name="max" value="60"/>
    </module>

## Further Reading

* [checkstyle - AnonInnerLength](http://checkstyle.sourceforge.net/config_sizes.html#AnonInnerLength)