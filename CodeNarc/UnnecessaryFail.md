Pattern: Unnecessary `Assert.fail()`

Issue: -

## Description

In a unit test, catching an exception and immediately calling `Assert.fail()` is pointless and hides the stack trace. It is better to re-throw the exception or not catch the exception at all.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

Example of violations:

``` groovy
public void testSomething() {
    try {
        something()
    } catch (Exception e) {
        fail(e.message)
    }

    try {
        something()
    } catch (Exception e) {
        fail()
    }
}
```

## Further Reading

* [CodeNarc - UnnecessaryFail](http://codenarc.sourceforge.net/codenarc-rules-junit.html#UnnecessaryFail)