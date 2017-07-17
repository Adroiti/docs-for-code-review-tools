Pattern: Missing Javadoc comment for variable

Issue: -

## Description

Checks that variables have Javadoc comments. Ignores `serialVersionUID` fields. 

## Examples

To configure the default check: 
    
    
    <module name="JavadocVariable"/>
            

To configure the check for `public` scope: 
    
    
    <module name="JavadocVariable">
       <property name="scope" value="public"/>
    </module>
            

To configure the check for members which are in `private`, but not in `protected` scope: 
    
    
    <module name="JavadocVariable">
       <property name="scope" value="private"/>
       <property name="excludeScope" value="protected"/>
    </module>
            

To ignore absence of Javadoc comments for variables with names `log` or `logger`: 
    
    
    <module name="JavadocVariable">
        <property name="ignoreNamePattern" value="log|logger"/>
    </module>

## Further Reading

* [checkstyle - JavadocVariable](http://checkstyle.sourceforge.net/config_javadoc.html#JavadocVariable)