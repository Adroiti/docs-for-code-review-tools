Pattern: Missing explicit field type

Issue: -

## Description

Checks that field types are explicitly specified (and not using `def`).

Example of violations:

``` groovy
class MyClass {
    public static final NAME = "joe"        // violation
    private static count = 0                // violation

    private def name = NAME                 // violation
    protected final date = new Date()       // violation

    def defaultName                         // violation
    def maxSoFar = -1L                      // violation
}
```

## Further Reading

* [CodeNarc - FieldTypeRequired](https://codenarc.github.io/CodeNarc/codenarc-rules-convention.html#fieldtyperequired-rule)