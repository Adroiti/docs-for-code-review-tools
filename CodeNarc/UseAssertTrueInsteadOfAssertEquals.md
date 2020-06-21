Pattern: `assertEquals` with boolean

Issue: -

## Description

This rule detects JUnit calling `assertEquals` where the first parameter is a boolean. These assertions should be made by more specific methods, like `assertTrue` or `assertFalse`.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

| **Property**          | **Description**                                                        | **Default Value** |
| --- | --- | --- |
| checkAssertStatements | If `true`, then also check assert statements, e.g. `assert x == true`. | `false`           |

All of the following examples can be simplified to assertTrue or remove the true literal:

``` groovy
assertEquals(true, foo())
assertEquals("message", true, foo())
assertEquals(foo(), true)
assertEquals("message", foo(), true)
assertEquals(false, foo())
assertEquals("message", false, foo())
assertEquals(foo(), false)
assertEquals("message", foo(), false)

assert true == foo()                    // violation only if checkAssertStatements == true
assert foo() == true : "message"        // violation only if checkAssertStatements == true
assert false == foo()                   // violation only if checkAssertStatements == true
assert foo() == false : "message"       // violation only if checkAssertStatements == true
```

## Further Reading

* [CodeNarc - UseAssertTrueInsteadOfAssertEquals](https://codenarc.github.io/CodeNarc/codenarc-rules-junit.html#useasserttrueinsteadofassertequals-rule)