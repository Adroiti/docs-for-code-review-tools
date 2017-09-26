Pattern: `assertTrue`/`assertFalse` with `Object#is()`

Issue: -

## Description

This rule detects JUnit calling `assertTrue` or `assertFalse` where the first or second parameter is an `Object#is()` call testing for reference equality. These assertion should be made against the `assertSame` or `assertNotSame` method instead.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

## Further Reading

* [CodeNarc - UseAssertSameInsteadOfAssertTrue](http://codenarc.sourceforge.net/codenarc-rules-junit.html#UseAssertSameInsteadOfAssertTrue)