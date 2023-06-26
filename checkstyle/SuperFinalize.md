Pattern: Missing `super.finalize()` call

Issue: -

## Description

Checks that an overriding `finalize()` method invokes `super.finalize()`. Does not check native methods, as they have no possible java defined implementation. 

Reference: [Use Finalization Only When You Must](http://www.oracle.com/technetwork/java/javamail/finalization-137655.html). 

## Examples

To configure the check: 


```xml
<module name="SuperFinalize"/>
```

## Further Reading

* [checkstyle - SuperFinalize](https://checkstyle.sourceforge.io/checks/coding/superfinalize.html#SuperFinalize)
