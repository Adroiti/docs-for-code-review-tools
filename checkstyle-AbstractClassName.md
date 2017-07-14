Pattern: Ensure that the names of abstract classes conforms to some regular expression.

Issue: -

## Description

Validates identifiers for `abstract` classes.

## Examples

The following example shows how to configure the `AbstractClassName` to checks names, but ignore missing `abstract` modifiers: 
    
    
    <module name="AbstractClassName">
      <property name="ignoreModifier" value="true"/>
    </module>

## Further Reading

* [checkstyle - AbstractClassName](http://checkstyle.sourceforge.net/config_naming.html#AbstractClassName)