Pattern: Use of `==` or `!=` for literal string equality

Issue: -

## Description

Checks that string literals are not used with `==` or `!=`. 

Rationale: Novice Java programmers often use code like: 


```java
if (x == "something")
```
        

when they mean


```java
if ("something".equals(x))
```
        

## Examples

To configure the check: 


```xml
<module name="StringLiteralEquality"/>
```

## Further Reading

* [checkstyle - StringLiteralEquality](https://checkstyle.sourceforge.io/checks/coding/stringliteralequality.html#StringLiteralEquality)
