Pattern: Use of non-public method before public method

Issue: -

## Description

Enforces that all public methods are above protected and private methods.

Example of violations:

``` groovy
class MyClass {
    public static int staticMethod1() { }

    protected String method1() { }

    static final String staticMethod2() { }     // violation
    public String method2() { }                 // violation

    private int method3(int id) { }
}
```

## Further Reading

* [CodeNarc - PublicMethodsBeforeNonPublicMethods](https://codenarc.github.io/CodeNarc/codenarc-rules-convention.html#publicmethodsbeforenonpublicmethods-rule)