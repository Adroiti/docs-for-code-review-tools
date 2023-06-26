Pattern: Use of verbose boolean return

Issue: -

## Description

Checks for over-complicated boolean return statements. For example the following code:


```java
if (valid())
    return false;
else
    return true;
```
        

could be written as:


```java
return !valid();
```


This change will make the code more succinct and clear to the readers.
        

		
## Default configuration

```xml
<module name="SimplifyBooleanReturn"/>
```

## Further Reading

* [checkstyle - SimplifyBooleanReturn](https://checkstyle.sourceforge.io/checks/coding/simplifybooleanreturn.html#SimplifyBooleanReturn)
