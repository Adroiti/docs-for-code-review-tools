Pattern: Top-level class not in separate source file

Issue: -

## Description

Checks that each top-level class, interface or enum resides in a source file of its own. If file doesn't contain public class, enum or interface, top-level type is the first type in file.

## Examples

An example of check's configuration:

```xml
<module name="OneTopLevelClass"/>
```


**ATTENTION:** This check does not support customization of validated tokens, so do not use the "tokens" property. 

An example of code with violations:

```java
public class Foo{
    //methods
}

class Foo2{
    //methods
}
```


An example of code without public top-level type:

```java
class Foo{ // top-level class
    //methods
}

class Foo2{
    //methods
}
```


An example of code without violations:

```java
public class Foo{
    //methods
}
```


## Further Reading

* [Java Language Specification - Top Level Type Declarations](http://docs.oracle.com/javase/specs/jls/se7/html/jls-7.html#jls-7.6)
* [checkstyle - OneTopLevelClass](http://checkstyle.sourceforge.net/config_design.html#OneTopLevelClass)
