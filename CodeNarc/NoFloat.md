Pattern: Use of `float`/`Float`

Issue: -

## Description

Checks for use of the `float` or `java.lang.Float` types, in fields, variables, method parameters, constructor parameters and method return types.
Prefer using BigDecimal or int or long, when exact calculations are required. This is due to the limitations and gotchas of the floating point representation
of the *float* type. This is especially important for monetary calculations.

Example of violations:

```groovy
    class MyClass {
        int count
        float floatProperty                                 // Violation: Property (field) type
        private Float floatField = 1.2                      // Violation: Field type

        private float calculateAverage() { return 0 }       // Violation: Method return type

        protected void setAverage(Float average) { }        // Violation: Method parameter type

        MyClass(int count, float rating, float factor) {    // Violation: Constructor parameter
            String name = 'abc'
            Float floatVar = calculateAverage()             // Violation: Variable
            float float1, float2 = 0                        // Violation: Variable
        }
    }
```