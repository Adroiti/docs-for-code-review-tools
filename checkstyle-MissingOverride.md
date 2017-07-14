Pattern: This class is used to verify that the java.lang.Override annotation is present when the {@inheritDoc} javadoc tag is present.

Issue: -

## Description

Verifies that the java.lang.Override annotation is present when the {@inheritDoc} javadoc tag is present.

## Examples

To configure the check:
    
    
     <module name="MissingOverride"/>
            

To configure the check for the `javaFiveCompatibility` mode: 
    
    
       <module name="MissingOverride">
          <property name="javaFiveCompatibility"
              value="true"/>
       </module>

## Further Reading

* [checkstyle - MissingOverride](http://checkstyle.sourceforge.net/config_annotation.html#MissingOverride)