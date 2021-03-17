Pattern: Malformed pattern variable name

Issue: -

## Description

Checks that pattern variable names conform to a specified pattern. 

## Examples

```java
class MyClass {
    MyClass(Object o1){
        if (o1 instanceof String STRING) { // violation, name 'STRING' must
        // match pattern '^[a-z][a-zA-Z0-9]*$'
        }
        if (o1 instanceof Integer num) { // OK
        }
    }
}
     
```

## Further Reading

* [checkstyle - PatternVariableName](http://checkstyle.sourceforge.net/config_naming.html#PatternVariableName)