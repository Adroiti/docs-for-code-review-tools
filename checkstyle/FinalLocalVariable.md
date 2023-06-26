Pattern: Local variable not declared as final

Issue: -

## Description

Checks that local variables that never have their values changed are declared final. The check can be configured to also check that unchanged parameters are declared final.

## Examples

To configure the check: 


```xml
<module name="FinalLocalVariable"/>
```
        

To configure the check so that it checks local variables and parameters: 


```xml
<module name="FinalLocalVariable">
    <property name="tokens" value="VARIABLE_DEF,PARAMETER_DEF"/>
</module>
```
        

By default, this check skip final validation on [Enhanced For-Loop](http://docs.oracle.com/javase/specs/jls/se8/html/jls-14.html#jls-14.14.2). 

Option 'validateEnhancedForLoopVariable' could be used to make check to validate even variable from Enhanced For Loop. 

An example of how to configure the check so that it also validates enhanced For Loop Variable is: 


```java
 <module name="FinalLocalVariable">
     <property name="tokens" value="VARIABLE_DEF"/>
     <property name="validateEnhancedForLoopVariable" value="true"/>
 </module>
```


Example:


```java
for (int number : myNumbers) { // violation
System.out.println(number);
}
```

## Further Reading

* [checkstyle - FinalLocalVariable](https://checkstyle.sourceforge.io/checks/coding/finallocalvariable.html#FinalLocalVariable)
