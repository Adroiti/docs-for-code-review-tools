Pattern: JUnit - public property

Issue: -

## Description

Checks for public properties defined on JUnit test classes. There is typically no need to expose a public property (with public *getter* and *setter* methods) on a test class.

This rule sets the default value of the *applyToClassNames* property to only match class names ending in 'Test', 'Tests' or 'TestCase'.

| **Property**        | **Description**                                                                                                                                                                  | **Default Value** |
| --- | --- | --- |
| ignorePropertyNames | Specifies one or more (comma-separated) property names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?). | `null`            |

Example of violations:

``` groovy
import org.junit.Test
class SomeTestCase {
    static String id    // violation
    def helper          // violation
    String name         // violation

    @Test
    void testMe() { }
}
```

## Further Reading

* [CodeNarc - JUnitPublicProperty](http://codenarc.sourceforge.net/codenarc-rules-junit.html#JUnitPublicProperty)