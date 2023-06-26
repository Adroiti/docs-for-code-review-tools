Pattern: Use of inline conditional

Issue: -

## Description

Detects inline conditionals. Here is one example of an inline conditional: 


```java
String a = getParameter("a");
String b = (a==null || a.length<1) ? null : a.substring(1);
```
        

Rationale: Some developers find inline conditionals hard to read, so their employer's coding standards forbid them. 

## Examples

To configure the check: 


```xml
<module name="AvoidInlineConditionals"/>
```

## Further Reading

* [checkstyle - AvoidInlineConditionals](https://checkstyle.sourceforge.io/checks/coding/avoidinlineconditionals.html#AvoidInlineConditionals)
