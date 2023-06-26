Pattern: Too many parameters for method or constructor

Issue: -

## Description

Checks the number of parameters of a method or constructor. 

## Examples

To configure the check: 


```xml
<module name="ParameterNumber"/>
```
        

To configure the check to allow 10 parameters for a method: 


```xml
<module name="ParameterNumber">
   <property name="max" value="10"/>
   <property name="tokens" value="METHOD_DEF"/>
</module>
```
        

To configure the check to ignore number of parameters for methods with `@Override` or `@java.lang.Override` annotation. 

Rationale: developer may need to override method with many parameters from 3-rd party library. In this case developer has no control over number of parameters. 


```xml
<module name="ParameterNumber">
    <property name="ignoreOverriddenMethods" value="true"/>
    <property name="tokens" value="METHOD_DEF"/>
</module>
```
 

Java code example 


```java
@Override
public void needsLotsOfParameters(int a, int b, int c, int d, int e, int f, int g, int h) {
    ...
}
```

## Further Reading

* [checkstyle - ParameterNumber](https://checkstyle.sourceforge.io/checks/sizes/parameternumber.html#ParameterNumber)
