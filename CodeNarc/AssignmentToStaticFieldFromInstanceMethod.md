Pattern: Assignment to static field from instance method

Issue: -

## Description

Checks for assignment to a static field from an instance method.

Example of violations:

``` groovy
class SomeClass {
    private static field1
    protected static String field2 = 'abc'
    public static int field3 = 123
    static String property1 = 'abc'
    private static final NAME = 'joe'

    private void doStuff() {
        field1 = new Object()       // violation
        field2 = 'xxx'              // violation
        field3 = 999                // violation
        property1 = 'xxx'           // violation

        final NAME = 'martin'       // no violation; local var hides static field
    }
}
```

## Further Reading

* [CodeNarc - AssignmentToStaticFieldFromInstanceMethod](http://codenarc.sourceforge.net/codenarc-rules-design.html#AssignmentToStaticFieldFromInstanceMethod)