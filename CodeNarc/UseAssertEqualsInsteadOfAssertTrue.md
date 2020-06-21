Pattern: Misused object equality assertion

Issue: -

## Description

This rule detects JUnit assertions in object equality. These assertions should be made by more specific methods, like `assertEquals`.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

## Further Reading

* [CodeNarc - UseAssertEqualsInsteadOfAssertTrue](https://codenarc.github.io/CodeNarc/codenarc-rules-junit.html#useassertequalsinsteadofasserttrue-rule)