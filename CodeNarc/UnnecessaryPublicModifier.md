Pattern: Unnecessary `public` modifier

Issue: -

## Description

The `public` modifier is not required on methods, constructors or classes.

Because of Groovy parsing limitations, this rule ignores methods (and constructors) that include Generic types in the method declaration.

Example of violations:

``` groovy
// violation on class
public class MyClass {
    // violation on constructor
    public MyClass() {}

    // violation on method
    public void myMethod() {}
}
```

## Further Reading

* [CodeNarc - UnnecessaryPublicModifier](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryPublicModifier)