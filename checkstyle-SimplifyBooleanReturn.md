Pattern: Overly complicated boolean return statement

Issue: -

## Description

Checks for over-complicated boolean return statements. For example the following code 


```java
if (valid())
    return false;
else
    return true;
```
        

could be written as 


```java
return !valid();
```
        

## Examples

To configure the check: 


```xml
<module name="SimplifyBooleanReturn"/>
```

## Further Reading

* [checkstyle - SimplifyBooleanReturn](http://checkstyle.sourceforge.net/config_coding.html#SimplifyBooleanReturn)
