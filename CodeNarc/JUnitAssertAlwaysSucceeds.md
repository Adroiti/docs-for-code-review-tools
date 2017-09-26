Pattern: JUnit - `assert()` always succeeds

Issue: -

## Description

Rule that checks for JUnit `assert()` method calls with constant arguments such that the assertion always succeeds. This includes:

-   `assertTrue(true)`
-   `assertTrue(99)`
-   `assertTrue('abc')`
-   `assertTrue([123])`
-   `assertTrue([a:123])`
-   `assertFalse(false)`
-   `assertFalse('')`
-   `assertFalse(0)`
-   `assertFalse([])`
-   `assertFalse([:)`
-   `assertNull(null)`

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

## Further Reading

* [CodeNarc - JUnitAssertAlwaysSucceeds](http://codenarc.sourceforge.net/codenarc-rules-junit.html#JUnitAssertAlwaysSucceeds)