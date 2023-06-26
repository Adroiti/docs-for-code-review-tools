Pattern: Use of multiple variable declarations

Issue: -

## Description

Checks that each variable declaration is in its own statement and on its own line. 

Rationale: [the Java code conventions chapter 6.1](http://www.oracle.com/technetwork/java/javase/documentation/codeconventions-141270.html#2992) recommends that declarations should be one per line/statement. 

## Examples

To configure the check: 


```xml
<module name="MultipleVariableDeclarations"/>
```

## Further Reading

* [Google Java Style Guide - Variable declarations](https://google.github.io/styleguide/javaguide.html#s4.8.2-variable-declarations)
* [checkstyle - MultipleVariableDeclarations](https://checkstyle.sourceforge.io/checks/coding/multiplevariabledeclarations.html#MultipleVariableDeclarations)
