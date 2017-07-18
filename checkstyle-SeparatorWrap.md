Pattern: Wrong line wrapping with separators

Issue: -

## Description

Checks line wrapping with separators. 

## Examples

Code example for comma and dot at the new line: 


```java
s
    .isEmpty();
foo(i
    ,s);
```
        

An example of how to configure the check is: 


```xml
<module name="SeparatorWrap"/>
```
        

Code example for comma and dot at the previous line: 


```java
s.
    isEmpty();
foo(i,
    s);
```
        

Example for checking method reference at new line (good case and bad case): 


```java
Arrays.sort(stringArray, String:: // violation
    compareToIgnoreCase);
Arrays.sort(stringArray, String
    ::compareToIgnoreCase); // good
```
        

An example of how to configure the check for [METHOD_REF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#METHOD_REF) at new line: 


```xml
<module name="SeparatorWrap">
    <property name="tokens" value="METHOD_REF"/>
    <property name="option" value="nl"/>
</module>
```
        

An example of how to configure the check for comma at the new line is: 


```xml
<module name="SeparatorWrap">
    <property name="tokens" value="COMMA"/>
    <property name="option" value="nl"/>
</module>
```

## Further Reading

* [checkstyle - SeparatorWrap](http://checkstyle.sourceforge.net/config_whitespace.html#SeparatorWrap)
