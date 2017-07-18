Pattern: Too many `return` statements

Issue: -

## Description

Restricts the number of return statements in methods, constructors and lambda expressions (2 by default). Ignores specified methods (`equals()` by default). 

**max** property will only check returns in methods and lambdas that return a specific value (Ex: 'return 1;'). 

**maxForVoid** property will only check returns in methods, constructors, and lambdas that have no return type (IE 'return;'). It will only count visible return statements. Return statements not normally written, but implied, at the end of the method/constructor definition will not be taken into account. To disallow "return;" in void return type methods, use a value of 0. 

Rationale: Too many return points can mean that code is attempting to do too much or may be difficult to understand. 

## Examples

To configure the check so that it doesn't allow more than three return statements per method (ignoring the `equals()` method): 


```xml
<module name="ReturnCount">
    <property name="max" value="3"/>
</module>
```
        

To configure the check so that it doesn't allow any return statements per void method: 


```xml
<module name="ReturnCount">
    <property name="maxForVoid" value="0"/>
</module>
```
        

To configure the check so that it doesn't allow more than 2 return statements per method (ignoring the `equals()` method) and more than 1 return statements per void method: 


```xml
<module name="ReturnCount">
    <property name="max" value="2"/>
    <property name="maxForVoid" value="1"/>
</module>
```
        

To configure the check so that it doesn't allow more than three return statements per method for all methods: 


```xml
<module name="ReturnCount">
    <property name="max" value="3"/>
    <property name="format" value="^$"/>
</module>
```
        

To configure the check so that it doesn't allow any return statements in constructors, more than one return statement in all lambda expressions and more than two return statements in methods: 


```xml
<module name="ReturnCount">
    <property name="max" value="0"/>
    <property name="tokens" value="CTOR_DEF"/>
</module>
<module name="ReturnCount">
    <property name="max" value="1"/>
    <property name="tokens" value="LAMBDA"/>
</module>
<module name="ReturnCount">
    <property name="max" value="2"/>
    <property name="tokens" value="METHOD_DEF"/>
</module>
```

## Further Reading

* [checkstyle - ReturnCount](http://checkstyle.sourceforge.net/config_coding.html#ReturnCount)
