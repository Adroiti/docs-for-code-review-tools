Pattern: JUnit - public non-test method

Issue: -

## Description

Rule that checks if a JUnit test class contains public methods other than standard test methods, JUnit framework methods or methods with JUnit annotations.

The following public methods are ignored by this rule:

-   Zero-argument methods with names starting with "test"
-   The `setUp()` and `tearDown()` methods
-   Methods annotated with `@Test`
-   Methods annotated with `@Before` and `@After`
-   Methods annotated with `@BeforeClass` and `@AfterClass`
-   Methods annotated with `@Override`

Public, non-test methods on a test class violate conventional usage of test classes, and they typically break encapsulation unnecessarily.

Public, non-test methods may also hide unintentional *'Lost Tests'*. For instance, the test method declaration may (unintentionally) include methods parameters, and thus be ignored by JUnit. Or the method may (unintentionally) not follow the "test.." naming convention and not have the @Test annotation, and thus be ignored by JUnit.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

## Further Reading

* [CodeNarc - JUnitPublicNonTestMethod](https://codenarc.github.io/CodeNarc/codenarc-rules-junit.html#junitpublicnontestmethod-rule)