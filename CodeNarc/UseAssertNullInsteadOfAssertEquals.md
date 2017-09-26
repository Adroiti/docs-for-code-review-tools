Pattern: `assertEquals()` with `null`

Issue: -

## Description

This rule detects JUnit calling `assertEquals` where the first or second parameter is `null`. These assertion should be made against the `assertNull` method instead.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

## Further Reading

* [CodeNarc - UseAssertNullInsteadOfAssertEquals](http://codenarc.sourceforge.net/codenarc-rules-junit.html#UseAssertNullInsteadOfAssertEquals)