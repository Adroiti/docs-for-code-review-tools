Pattern: Missing `super.clone()` call

Issue: -

## Description

Checks that an overriding `clone()` method invokes `super.clone()`. Does not check native methods, as they have no possible java defined implementation. 

Reference: [Object.clone()](https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html#clone%28%29). 

## Examples

To configure the check: 


```xml
<module name="SuperClone"/>
```

## Further Reading

* [checkstyle - SuperClone](https://checkstyle.sourceforge.io/checks/coding/superclone.html#SuperClone)
