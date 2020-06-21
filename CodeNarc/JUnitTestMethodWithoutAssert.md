Pattern: JUnit - test method without assert

Issue: -

## Description

This rule searches for test methods that do not contain assert statements. Either the test method is missing assert statements, which is an error, or the test method contains custom assert statements that do not follow a proper assert naming convention. Test methods are defined as public void methods that begin with the work test or have a `@Test` annotation. 

By default this rule applies to the default test class names, but this can be changed using the rule's `applyToClassNames` property. An assertion is defined as either using the `assert` keyword or invoking a method that starts with the work assert, like `assertEquals` or `assertNull`. Also, any method named `should.*` also counts as an assertion so that `shouldFail` methods do not trigger an assertion, any method that starts with `fail>> counts as an assertion, and any method that starts with <<<verify` counts as an assertion.

What counts as an assertion method can be overridden using the `assertMethodPatterns` property of the rule. The default value is this comma separated list of regular expressions:

``` groovy
String assertMethodPatterns = 'assert.*,should.*,fail.*,verify.*,expect.*'
```

If you'd like to add any method starting with 'ensure' to the ignores then you would set the value to this:

``` groovy
'assert.*,should.*,fail.*,verify.*,ensure.*'
```

## Further Reading

* [CodeNarc - JUnitTestMethodWithoutAssert](https://codenarc.github.io/CodeNarc/codenarc-rules-junit.html#junittestmethodwithoutassert-rule)