Pattern: JUnit - `assert()` always fails

Issue: -

## Description

Rule that checks for JUnit `assert()` method calls with constant or literal arguments such that the assertion always fails. This includes:

-   `assertTrue(false)`
-   `assertTrue(0)`
-   `assertTrue('')`
-   `assertTrue([])`
-   `assertTrue([:])`
-   `assertFalse(true)`
-   `assertFalse('abc')`
-   `assertFalse(99)`
-   `assertFalse([123])`
-   `assertFalse([a:123)`
-   `assertNull(CONSTANT)`.
-   `assertNull([])`.
-   `assertNull([123])`.
-   `assertNull([:])`.
-   `assertNull([a:123])`.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

## Further Reading

* [CodeNarc - JUnitAssertAlwaysFails](http://codenarc.sourceforge.net/codenarc-rules-junit.html#JUnitAssertAlwaysFails)