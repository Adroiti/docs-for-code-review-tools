Pattern: Incorrect indentation

Issue: -

## Description

Checks correct indentation of Java code. 

The idea behind this is that while pretty printers are sometimes convenient for bulk reformats of legacy code, they often either aren't configurable enough or just can't anticipate how format should be done. Sometimes this is personal preference, other times it is practical experience. In any case, this check should just ensure that a minimal set of indentation rules is followed. 

## Examples

To configure the check: 


```xml
<module name="Indentation"/>
```
        

To configure the check to enforce the indentation style recommended by Oracle: 


```xml
<module name="Indentation">
    <property name="caseIndent" value="0"/>
</module>
```
        

To configure the check to enforce strict condition in line-wrapping validation. 


```xml
<module name="Indentation">
    <property name="forceStrictCondition" value="true"/>
</module>
```
        

Such config doesn't allow next cases: 


```java
void foo(String aFooString,
        int aFooInt) {} // indent:8 ; expected: 4; warn, because 8 != 4
```
        

But if forceStrictCondition = false, this code is valid: 


```java
void foo(String aFooString,
        int aFooInt) {} // indent:8 ; expected: > 4; ok, because 8 > 4
```

## Further Reading

* [checkstyle - Indentation](https://checkstyle.sourceforge.io/checks/misc/indentation.html#Indentation)
