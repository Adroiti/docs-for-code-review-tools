Pattern: Variable declaration is distanced from it's first usage

Issue: -

## Description

This rule enforces recommentation by Google Java Style Guide - local variables should not be habitually declared at the start of their containing block or block-like construct. Instead, local variables should be declared close to the point they are first used (within reason), to minimize their scope.

Local variable declarations typically have initializers, or are initialized immediately after declaration. Consider making variable final if you still need to store its value in advance (before method calls that might have side effects on the original value).

## Examples

Example #1: 


```java
int count;
a = a + b;
b = a + a;
count = b; // DECLARATION OF VARIABLE 'count'
  // SHOULD BE HERE (distance = 3)
```
        

Example #2: 


```java
int count;
{
     a = a + b;
     count = b; // DECLARATION OF VARIABLE 'count'
   // SHOULD BE HERE (distance = 2)
}
```
        

Check can detect a block of initialization methods. If a variable is used in such a block and there is no other statements after this variable then distance=1. 

Case #1: 


```java
int minutes = 5;
Calendar cal = Calendar.getInstance();
cal.setTimeInMillis(timeNow);
cal.set(Calendar.SECOND, 0);
cal.set(Calendar.MILLISECOND, 0);
cal.set(Calendar.HOUR_OF_DAY, hh);
cal.set(Calendar.MINUTE, minutes);
```
        

The distance for the variable minutes is 1 even though this variable is used in the fifth method's call. 

Case #2: 


```java
int minutes = 5;
Calendar cal = Calendar.getInstance();
cal.setTimeInMillis(timeNow);
cal.set(Calendar.SECOND, 0);
cal.set(Calendar.MILLISECOND, 0);
System.out.println(cal);
cal.set(Calendar.HOUR_OF_DAY, hh);
cal.set(Calendar.MINUTE, minutes);
```


The distance for the variable minutes is 6 because there is one more expression (except the initialization block) between the declaration of this variable and its usage. 

An example how to configure this check: 


```xml
<module name="VariableDeclarationUsageDistance"/>
```


An example of how to configure this check: 
- to set the allowed distance to `4`; 
- to ignore variables with prefix `^temp`;
- to force the validation between scopes; 
- to check the final variables; 

```xml
<module name="VariableDeclarationUsageDistance">
    <property name="allowedDistance" value="4"/>
    <property name="ignoreVariablePattern" value="^temp.*"/>
    <property name="validateBetweenScopes" value="true"/>
    <property name="ignoreFinal" value="false"/>
</module>
```

## Further Reading

* [Google Java Style Guide - Variable declarations](https://google.github.io/styleguide/javaguide.html#s4.8.2-variable-declarations)
* [checkstyle - VariableDeclarationUsageDistance](http://checkstyle.sourceforge.net/config_coding.html#VariableDeclarationUsageDistance)
