Pattern: To many `throw` statements

Issue: -

## Description

Restricts `throw` statements to a specified count (4 by default). Methods with `Override` or `java.lang.Override` annotation are skipped from validation as current class cannot change signature of these methods. 

Rationale: Exceptions form part of a method's interface. Declaring a method to throw too many differently rooted exceptions makes exception handling onerous and leads to poor programming practices such as writing code like `catch(Exception ex)`. 4 is the empirical value which is based on reports that we had for the `ThrowsCountCheck` over big projects such as _OpenJDK_. This check also forces developers to put exceptions into a hierarchy such that in the simplest case, only one type of exception need be checked for by a caller but any subclasses can be caught specifically if necessary. For more information on rules for the exceptions and their issues, see _Effective Java: Programming Language Guide Second Edition by Joshua Bloch pages 264-273_. 

**ignorePrivateMethods** \- allows to skip private methods as they do not cause problems for other classes. 

## Examples

To configure the check so that it doesn't allow more than two throws per method: 


```xml
<module name="ThrowsCount">
    <property name="max" value="2"/>
</module>
```
        

To configure the check so that it doesn't skip private methods: 


```xml
<module name="ThrowsCount">
    <property name="ignorePrivateMethods" value="false"/>
</module>
```

## Further Reading

* [checkstyle - ThrowsCount](https://checkstyle.sourceforge.io/checks/design/throwscount.html#ThrowsCount)
