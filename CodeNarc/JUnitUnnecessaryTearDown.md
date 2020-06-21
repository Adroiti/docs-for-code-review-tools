Pattern: JUnit - unnecessary `tearDown()`

Issue: -

## Description

Rule that checks checks for JUnit `tearDown()` methods that contain only a call to `super.tearDown()`. The method is then unnecessary.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

Here is an example of a violation:

``` groovy
class SomeTest extends TestCase {
    void tearDown() {               // violation
        super.tearDown()
    }
}
```

## Further Reading

* [CodeNarc - JUnitUnnecessaryTearDown](https://codenarc.github.io/CodeNarc/codenarc-rules-junit.html#junitunnecessaryteardown-rule)