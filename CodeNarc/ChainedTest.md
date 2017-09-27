Pattern: Chained test

Issue: -

## Description

A test method that invokes another test method is a chained test; the methods are dependent on one another. Tests should be isolated, and not be dependent on one another.

Example of violations:

``` groovy
class SomeTest extends GroovyTestCase {
    public void testFoo() {

        // violations, calls test method on self
        5.times { testBar() }
        5.times { this.testBar() }

        // OK, no violation: one arg method is not actually a test method
        5.times { testBar(it) }
    }

    private static void assertSomething() {
        testBar() // violation, even if in helper method
        this.testBar() // violation, even if in helper method
    }

    public void testBar() {
        // ...
    }
}
```

## Further Reading

* [CodeNarc - ChainedTest](http://codenarc.sourceforge.net/codenarc-rules-junit.html#ChainedTest)