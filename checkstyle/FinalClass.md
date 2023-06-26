Pattern: Class not declared as final

Issue: -

## Description

Checks that a class which has only private constructors is declared as final. Doesn't check for classes nested in interfaces or annotations, as they are always `final` there. 

## Examples

To configure the check: 


```xml
<module name="FinalClass"/>
```

## Further Reading

* [checkstyle - FinalClass](https://checkstyle.sourceforge.io/checks/design/finalclass.html#FinalClass)
