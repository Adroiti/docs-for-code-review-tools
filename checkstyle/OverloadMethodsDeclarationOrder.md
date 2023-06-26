Pattern: Overload methods are not grouped together

Issue: -

## Description

Methods with the same name should appear sequentially to improve code readability.

## Default configuration

```xml
<module name="OverloadMethodsDeclarationOrder"/>
```

## Examples

Example of **incorrect** code:

```java
public void foo(int i) {}
public void foo(String s) {}
public void notFoo() {} // unrelated method
public void foo(int i, String s) {}
```
        
Example of **correct** code:


```java
public void foo(int i) {}
public void foo(String s) {}
public void foo(int i, String s) {}
public void notFoo() {}
```


## Further Reading

* [Google Java Style Guide - Ordering of class contents](https://google.github.io/styleguide/javaguide.html#s3.4.2-ordering-class-contents)
* [checkstyle - OverloadMethodsDeclarationOrder](https://checkstyle.sourceforge.io/checks/coding/overloadmethodsdeclarationorder.html#OverloadMethodsDeclarationOrder)
