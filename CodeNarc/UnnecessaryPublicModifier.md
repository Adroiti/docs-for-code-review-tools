Pattern: Unnecessary `public` modifier

Issue: -

## Description

The `public` modifier is not required on methods, constructors or classes.

Because of Groovy parsing limitations, this rule ignores methods (and constructors) that include Generic types in the method declaration.

Example of violations:

``` groovy
// violation on class
public class SomeClass {
    // violation on constructor
    public SomeClass() {}

    // violation on method
    public void someMethod() {}
}
```

## Further Reading

* [CodeNarc - UnnecessaryPublicModifier](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryPublicModifier)