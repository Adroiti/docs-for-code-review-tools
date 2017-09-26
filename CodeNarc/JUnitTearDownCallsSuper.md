Pattern: JUnit - missing call to `super.tearDown()`

Issue: -

## Description

Rule that checks that if the JUnit `tearDown` method is defined, that it includes a call to `super.tearDown()`.

This rule ignored methods annotated with `@After` or `@AfterClass`.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

## Further Reading

* [CodeNarc - JUnitTearDownCallsSuper](http://codenarc.sourceforge.net/codenarc-rules-junit.html#JUnitTearDownCallsSuper)