Pattern: Class used as type in variable declaration, return value or parameter

Issue: -

## Description

Checks that particular classes are never used as types in variable declarations, return values or parameters. 

Rationale: Helps reduce coupling on concrete classes. 

## Examples

To configure the check so that it ignores getInstance() methods: 


```xml
<module name="IllegalType">
    <property name="ignoredMethodNames" value="getInstance"/>
</module>
```
        

To configure the check so that it verifies only public, protected and static methods and fields: 


```xml
<module name="IllegalType">
    <property name="memberModifiers" value="LITERAL_PUBLIC,
     LITERAL_PROTECTED, LITERAL_STATIC"/>
</module>
```

## Further Reading

* [checkstyle - IllegalType](https://checkstyle.sourceforge.io/checks/coding/illegaltype.html#IllegalType)
