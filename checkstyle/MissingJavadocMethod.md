Pattern: Missing Javadoc comments for method/constructor

Issue: -

## Description

Checks for missing Javadoc comments for a method or constructor. The scope to verify is specified using the `Scope` class and defaults to `Scope.PUBLIC`.

Javadoc is not required on a method that is tagged with the `@Override` annotation. However under Java 5 it is not possible to mark a method required for an interface (this was _corrected_ under Java 6). Hence Checkstyle supports using the convention of using a single `{@inheritDoc}` tag instead of all the other tags. 

For getters and setters for the property `allowMissingPropertyJavadoc`, the methods must match exactly the structures below. 


## Examples

To configure the default check: 
    
    

    <module name="MissingJavadocMethod"/>

            

To configure the check for `private` scope: 
    
    
    

    <module name="MissingJavadocMethod">

      <property name="scope" value="private"/>

    </module>

            

To configure the check for methods which are in `private`, but not in `protected` scope: 
    
    
    

    <module name="MissingJavadocMethod">

      <property name="scope" value="private"/>

      <property name="excludeScope" value="protected"/>

    </module>

            

To configure the check for ignoring methods named `foo(),foo1(),foo2()`, etc.: 
    
    
    

    <module name="MissingJavadocMethod">

      <property name="ignoreMethodNamesRegex" value="^foo.*$"/>

    </module>

## Further Reading

* [checkstyle - MissingJavadocMethod](http://checkstyle.sourceforge.net/config_javadoc.html)