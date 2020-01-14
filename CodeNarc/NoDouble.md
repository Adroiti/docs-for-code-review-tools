Pattern: Use of `double`/`Double`

Issue: -

## Description

Checks for use of the `double` or `java.lang.Double` types, in fields, variables, method parameters, constructor parameters and method return types.
Prefer using BigDecimal or int or long, when exact calculations are required. This is due to the limitations and gotchas of the floating point representation
of the *double* type. This is especially important for monetary calculations.

Example of violations:

```groovy
    class CustomClass {
        int count
        double doubleProperty                               // Violation: Property (field) type
        private Double doubleField = 1.2                    // Violation: Field type

        private double calculateAverage() { return 0 }      // Violation: Method return type

        protected void setAverage(Double average) { }       // Violation: Method parameter type

        MyClass(int count, double rating, double factor) {  // Violation: Constructor parameter
            String name = 'abc'
            Double doubleVar = calculateAverage()           // Violation: Variable
            double double1, double2 = 0                     // Violation: Variable
        }
    }
```

## Further Reading

* [Why not use Double or Float to represent currency?](https://stackoverflow.com/questions/3730019/why-not-use-double-or-float-to-represent-currency)