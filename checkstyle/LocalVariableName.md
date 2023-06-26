Pattern: Invalid local, non-`final` variable name

Issue: -

## Description

Checks that local, non-`final` variable names conform to a format specified by the `format` property. 

## Examples

To configure the check to use the default configuration: 


```xml
<module name="LocalVariableName"/>
```
        

An example of how to configure the check to allow one character variable name in [initialization expressions](http://docs.oracle.com/javase/tutorial/java/nutsandbolts/for.html) in FOR loop: 


```xml
<module name="LocalVariableName">
    <property name="allowOneCharVarInForLoop" value="true"/>
</module>
```

## Further Reading

* [checkstyle - LocalVariableName](https://checkstyle.sourceforge.io/checks/naming/localvariablename.html#LocalVariableName)
