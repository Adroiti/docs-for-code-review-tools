Pattern: Outputs a JavaDoc tag as information

Issue: -

## Description

Requires user defined JavaDoc tag to be present in javadoc comment with defined format. To define the format for a tag, set property tagFormat to a regular expression. Property tagSeverity is used for severity of events when the tag exists. 

## Examples

An example of how to configure the check for printing author name is: 
    
    
    <module name="WriteTag">
       <property name="tag" value="@author"/>
       <property name="tagFormat" value="\S"/>
    </module>
            

An example of how to configure the check to print warnings if an "@incomplete" tag is found, and not print anything if it is not found: 
    
    
    <module name="WriteTag">
       <property name="tag" value="@incomplete"/>
       <property name="tagFormat" value="\S"/>
       <property name="severity" value="ignore"/>
       <property name="tagSeverity" value="warning"/>
    </module>

## Further Reading

* [checkstyle - WriteTag](http://checkstyle.sourceforge.net/config_javadoc.html#WriteTag)