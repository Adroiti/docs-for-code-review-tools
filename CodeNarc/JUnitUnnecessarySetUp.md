Pattern: JUnit - unnecessary `setUp()`

Issue: -

## Description

Rule that checks checks for JUnit `setUp()` methods that contain only a call to `super.setUp()`. The method is then unnecessary.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

Here is an example of a violation:

``` groovy
class SomeTest extends TestCase {
    void setUp() {              // violation
        super.setUp()
    }
}
```

## Further Reading

* [CodeNarc - JUnitUnnecessarySetUp](https://codenarc.github.io/CodeNarc/codenarc-rules-junit.html#junitunnecessarysetup-rule)