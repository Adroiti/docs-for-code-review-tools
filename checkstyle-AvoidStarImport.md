Pattern: Avoid star import

Issue: -

## Description

Checks that there are no import statements that use the * notation. 

Rationale: Importing all classes from a package or static members from a class leads to tight coupling between packages or classes and might lead to problems when a new version of a library introduces name clashes. 

## Examples

An example how to configure the check so that star imports from packages java.io and java.net as well as static members from class from java.lang.Math are allowed: 
    
    
    <module name="AvoidStarImport">
       <property name="excludes" value="java.io,java.net,java.lang.Math"/>
       <property name="allowClassImports" value="false"/>
       <property name="allowStaticMemberImports" value="false"/>
    </module>

## Further Reading

* [checkstyle - AvoidStarImport](http://checkstyle.sourceforge.net/config_imports.html#AvoidStarImport)