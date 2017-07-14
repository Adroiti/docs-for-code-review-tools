Pattern: Check that a JavaDoc block which can fit on a single line and doesn't contain at-clauses

Issue: -

## Description

Checks that a JavaDoc block can fit in a single line and doesn't contain at-clauses. Javadoc comment that contains at least one at-clause should be formatted in a few lines. 

## Examples

Default configuration: 
    
    
    <module name="SingleLineJavadoc"/>
            

To specify a list of ignored at-clauses and make inline at-clauses not ignored: 
    
    
    <module name="SingleLineJavadoc">
        <property name="ignoredTags" value="@inheritDoc, @see"/>
        <property name="ignoreInlineTags" value="false"/>
    </module>

## Further Reading

* [checkstyle - SingleLineJavadoc](http://checkstyle.sourceforge.net/config_javadoc.html#SingleLineJavadoc)