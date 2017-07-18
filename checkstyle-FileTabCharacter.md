Pattern: Use of tab character

Issue: -

## Description

Checks that there are no tab characters (`'\t'`) in the source code. 

Rationale: 

  - Developers should not need to configure the tab width of their text editors in order to be able to read source code. 
  - In a distributed development environment where diffs are sent to the mailing lists by both developers and the version control system (which sends commit log messages), the use tabs makes it impossible to preserve legibility.

## Examples

To configure the check to report on the first instance in each file: 
    
    
    <module name="FileTabCharacter"/>
            

To configure the check to report on each line in each file: 
    
    
    <module name="FileTabCharacter">
        <property name="eachLine" value="true"/>
    </module>

## Further Reading

* [Apache Commons - Coding Standards](https://commons.apache.org/proper/commons-net/code-standards.html)
* [checkstyle - FileTabCharacter](http://checkstyle.sourceforge.net/config_whitespace.html#FileTabCharacter)
