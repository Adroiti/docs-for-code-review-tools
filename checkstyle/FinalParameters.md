Pattern: Parameter is not declared as final

Issue: -

## Description

Check that parameters for methods, constructors, and catch blocks are final. Interface, abstract, and native methods are not checked: the `final` keyword does not make sense for interface, abstract, and native method parameters as there is no code that could modify the parameter. 

Rationale: Changing the value of parameters during the execution of the method's algorithm can be confusing and should be avoided. A great way to let the Java compiler prevent this coding style is to declare parameters final. 

## Examples

To configure the check to enforce final parameters for methods and constructors: 


```xml
<module name="FinalParameters"/>
```
        

To configure the check to enforce final parameters only for constructors: 


```xml
<module name="FinalParameters">
    <property name="tokens" value="CTOR_DEF"/>
</module>
```
        

To configure the check to allow ignoring [primitive datatypes](http://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html) as parameters: 


```xml
<module name="FinalParameters">
    <property name="ignorePrimitiveTypes" value="true"/>
</module>
```

## Further Reading

* [checkstyle - FinalParameters](https://checkstyle.sourceforge.io/checks/misc/finalparameters.html#FinalParameters)
