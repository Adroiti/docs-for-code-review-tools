Pattern: Duplicate keys in properties file

Issue: -

## Description

Checks properties files for duplicated keys. 

Rationale: Multiple property keys usually appear after merge or rebase of several branches. While there are no errors in runtime, there can be a confusion due to having different values for the duplicated properties. 

## Examples

To configure the check: 
    
    
    <module name="UniqueProperties">
        <property name="fileExtensions" value="properties" />
    </module>

## Further Reading

* [checkstyle - UniqueProperties](http://checkstyle.sourceforge.net/config_misc.html#UniqueProperties)