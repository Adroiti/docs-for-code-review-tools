Pattern: `assertFalse()` with the negation operator

Issue: -

## Description

In unit tests, if a condition is expected to be true then there is no sense using `assertFalse` with the negation operator. For instance, `assertFalse(!condition)` can always be simplified to `assertTrue(condition)`.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

## Further Reading

* [CodeNarc - UseAssertTrueInsteadOfNegation](http://codenarc.sourceforge.net/codenarc-rules-junit.html#UseAssertTrueInsteadOfNegation)