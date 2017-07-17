Pattern: Use of tab character

Issue: -

## Description

Checks that there are no tab characters (`'\t'`) in the source code. 

Rationale: 

  - Developers should not need to configure the tab width of their text editors in order to be able to read source code. 
  - From the Apache jakarta coding standards: In a distributed development environment, when the commit messages get sent to a mailing list, they are almost impossible to read if you use tabs. 

## Examples

To configure the check to report on the first instance in each file: 
    
    
    <module name="FileTabCharacter"/>
            

To configure the check to report on each line in each file: 
    
    
    <module name="FileTabCharacter">
        <property name="eachLine" value="true"/>
    </module>

## Further Reading

* [checkstyle - FileTabCharacter](http://checkstyle.sourceforge.net/config_whitespace.html#FileTabCharacter)