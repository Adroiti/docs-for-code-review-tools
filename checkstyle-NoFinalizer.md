Pattern: Use of `finalize()` method

Issue: -

## Description

This rule enforces recommendation by Google Java Style guide to avoid use of `finalize()` method. It is **extremely rare** to override `Object.finalize`.

## Examples

To configure the check: 


```xml
<module name="NoFinalizer"/>
```

## Further Reading

* [Google Java Style Guide - Finalizers: not used](https://google.github.io/styleguide/javaguide.html#s6.4-finalizers)
* [checkstyle - NoFinalizer](http://checkstyle.sourceforge.net/config_coding.html#NoFinalizer)
