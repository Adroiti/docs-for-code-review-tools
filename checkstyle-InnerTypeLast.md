Pattern: Fields and methods should be before inner classes

Issue: -

## Description

Check nested (inner) classes/interfaces are declared at the bottom of the class after all method and field declarations. 

## Examples

To configure the check: 


```xml
<module name="InnerTypeLast"/>
```

## Further Reading

* [checkstyle - InnerTypeLast](http://checkstyle.sourceforge.net/config_design.html#InnerTypeLast)
