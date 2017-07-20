Pattern: Top-level class not in separate source file

Issue: -

## Description

Each top-level class should reside in a source file of its own to avoid any confusion or misunderstanding. If file doesn't contain public class, enum or interface, top-level type is the first type in file.

## Default configuration

```xml
<module name="OneTopLevelClass"/>
```

## Examples

An example of code with violations:

```java
public class Foo{
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

* [Google Java Style Guide - Exactly one top-level class declaration](https://google.github.io/styleguide/javaguide.html#s3.4.1-one-top-level-class)
* [Java Language Specification - Top Level Type Declarations](http://docs.oracle.com/javase/specs/jls/se8/html/jls-7.html#jls-7.6)
* [checkstyle - OneTopLevelClass](http://checkstyle.sourceforge.net/config_design.html#OneTopLevelClass)
