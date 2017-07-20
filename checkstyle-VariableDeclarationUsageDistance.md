Pattern: Variable declaration is distanced from it's first usage

Issue: -

## Description

This rule enforces recommentation by Google Java Style Guide: Local variables should not be habitually declared at the start of their containing block or block-like construct. Instead, local variables should be declared close to the point they are first used (within reason), to minimize their scope.

Local variable declarations typically have initializers, or are initialized immediately after declaration. Consider making variable final if you still need to store its value in advance (before method calls that might have side effects on the original value).

## Default configuration

```xml
<module name="VariableDeclarationUsageDistance"/>
```

## Examples

Example of **incorrect** code:

```java
int minutes = 10;
doSomething();
doSomethingElse();
initialize();
Calendar cal = Calendar.getInstance();
cal.set(Calendar.MINUTE, minutes);
```
        
Example of **correct** code:

```java
doSomething();
doSomethingElse();
initialize();
Calendar cal = Calendar.getInstance();
int minutes = 10;
cal.set(Calendar.MINUTE, minutes);
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
