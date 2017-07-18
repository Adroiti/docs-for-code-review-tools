Pattern: Public or default constructor in utility class

Issue: -

## Description

Makes sure that utility classes (classes that contain only static methods or fields in their API) do not have a public constructor. 

Rationale: Instantiating utility classes does not make sense. Hence the constructors should either be private or (if you want to allow subclassing) protected. A common mistake is forgetting to hide the default constructor. 

If you make the constructor protected you may want to consider the following constructor implementation technique to disallow instantiating subclasses: 


```java
public class StringUtils // not final to allow subclassing
{
    protected StringUtils() {
        // prevents calls from subclass
        throw new UnsupportedOperationException();
    }
```

```java
    public static int count(char c, String s) {
        // ...
    }
}
```
        

## Examples

To configure the check: 


```xml
<module name="HideUtilityClassConstructor"/>
```

## Further Reading

* [checkstyle - HideUtilityClassConstructor](http://checkstyle.sourceforge.net/config_design.html#HideUtilityClassConstructor)
