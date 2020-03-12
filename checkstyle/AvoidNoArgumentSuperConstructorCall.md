Pattern: Redundant call to superclass constructor without arguments

Issue: -

## Description

Checks if call to superclass constructor without arguments is present. Such invocation is redundant because constructor body implicitly begins with a superclass constructor invocation `super();`.

## Examples

Example of violations:

```java
class MyClass extends SomeOtherClass {
    MyClass() {
        super(); // violation
    }

    MyClass(int arg) {
        super(arg); // OK, call with argument have to be explicit
    }

    MyClass(long arg) {
        // OK, call is implicit
    }
}
 
```

## Further Reading

* [checkstyle - AvoidNoArgumentSuperConstructorCall](http://checkstyle.sourceforge.net/config_coding.html#AvoidNoArgumentSuperConstructorCall)