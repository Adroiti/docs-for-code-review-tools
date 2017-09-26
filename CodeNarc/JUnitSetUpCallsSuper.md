Pattern: JUnit -  missing call to `super.setUp()`

Issue: -

## Description

Rule that checks that if the JUnit `setUp` method is defined, that it includes a call to `super.setUp()`.

This rule ignored methods annotated with `@Before` or `@BeforeClass`.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

## Further Reading

* [CodeNarc - JUnitSetUpCallsSuper](http://codenarc.sourceforge.net/codenarc-rules-junit.html#JUnitSetUpCallsSuper)