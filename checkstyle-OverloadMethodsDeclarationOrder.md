Pattern: Overload methods are not grouped together

Issue: -

## Description

Checks that overload methods are grouped together. 

## Examples

Example of incorrect grouping overload methods: 


```java
public void foo(int i) {}
public void foo(String s) {}
public void notFoo() {} // Have to be after foo(int i, String s)
public void foo(int i, String s) {}
```
        

An example of how to configure the check is: 


```xml
<module name="OverloadMethodsDeclarationOrder"/>
```

## Further Reading

* [checkstyle - OverloadMethodsDeclarationOrder](http://checkstyle.sourceforge.net/config_coding.html#OverloadMethodsDeclarationOrder)
