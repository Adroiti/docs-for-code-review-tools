Pattern: Empty method

Issue: -

## Description

A method was found without an implementation. If the method is overriding or implementing a parent method, then mark it with the `@Override` annotation. This rule should not be used with Java 5 code because you cannot put `@Override` on a method implementing an interface. Use with Java 6 and higher.

Example of violations:

``` groovy
class MyClass {

    // violation, empty method
    public void method1() {}

    // violation, empty method
    def method2() {}

    // OK because of @Override
    @Override
    public void method3() {}
}

abstract class MyBaseClass {
    // OK, handled by EmptyMethodInAbstractClass Rule
    public void method() {}
}
```

## Further Reading

* [CodeNarc - Empty method](http://codenarc.sourceforge.net/codenarc-rules-basic.html#EmptyMethod)