Pattern: Redundant `import` statement

Issue: -

## Description

Checks for redundant `import` statements. An `import` statement is considered redundant if: 

  - It is a duplicate of another import. This is, when a class is imported more than once. 
  - The class non-statically imported is from the `java.lang` package, e.g. importing `java.lang.String`. 
  - The class non-statically imported is from the same package as the current package. 

## Examples

To configure the check: 


```xml
<module name="RedundantImport"/>
```

## Further Reading

* [checkstyle - RedundantImport](http://checkstyle.sourceforge.net/config_imports.html#RedundantImport)
