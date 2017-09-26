Pattern: `assertTrue()` with negation operator

Issue: -

## Description

In unit tests, if a condition is expected to be false then there is no sense using `assertTrue` with the negation operator. For instance, `assertTrue(!condition)` can always be simplified to `assertFalse(condition)`.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

## Further Reading

* [CodeNarc - UseAssertFalseInsteadOfNegation](http://codenarc.sourceforge.net/codenarc-rules-junit.html#UseAssertFalseInsteadOfNegation)