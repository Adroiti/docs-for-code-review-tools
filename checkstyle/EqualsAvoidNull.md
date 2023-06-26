Pattern: Possibly unsafe `equals()` comparison

Issue: -

## Description

Checks that any combination of String literals is on the left side of an `equals()` comparison. Also checks for String literals assigned to some field (such as `someString.equals(anotherString = "text")`). 

Rationale: Calling the `equals()` method on String literals will avoid a potential `NullPointerException`. Also, it is pretty common to see null checks right before equals comparisons, which is not necessary in the example below. 

For example, this code: 


```java
String nullString = null;
nullString.equals("My_Sweet_String");
```
        

should be refactored to:


```java
String nullString = null;
"My_Sweet_String".equals(nullString);
```
        

## Examples

To configure the check: 


```xml
<module name="EqualsAvoidNull"/>
```

## Further Reading

* [checkstyle - EqualsAvoidNull](https://checkstyle.sourceforge.io/checks/coding/equalsavoidnull.html#EqualsAvoidNull)
