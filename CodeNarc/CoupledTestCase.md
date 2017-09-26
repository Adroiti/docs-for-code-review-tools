Pattern: Coupled test case

Issue: -

## Description

This rule finds test cases that are coupled to other test cases, either by invoking static methods on another test case or by creating instances of another test case. If you require shared logic in test cases then extract that logic to a new class where it can properly be reused. Static references to methods on the current test class are ignored.

Example of violations:

``` groovy
class MyTest extends GroovyTestCase {
    public void testMethod() {
        // violation, static method call to other test
        MyOtherTest.helperMethod()

        // violation, instantiation of another test class
        new MyOtherTest()

        // no violation; same class
        def input = MyTest.getResourceAsStream('sample.txt')
    }
}
```

## Further Reading

* [CodeNarc - CoupledTestCase](http://codenarc.sourceforge.net/codenarc-rules-junit.html#CoupledTestCase)