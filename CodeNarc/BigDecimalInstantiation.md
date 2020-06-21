Pattern: Big decimal instantiation

Issue: -

## Description

Checks for calls to the `java.math.BigDecimal` constructors that take a `double` value as the first parameter. As described in the `BigDecimal` javadoc, the results from these constructors can be somewhat unpredictable, and their use is generally not recommended. This is because some numbers, such as 0.1, cannot be represented exactly as a `double`.

For instance, executing `println new BigDecimal(0.1)` prints out `0.1000000000000000055511151231257827021181583404541015625`.

Here is an example of code that produces a violation:

``` groovy
def b1 = new BigDecimal(0.1)               // violation
def b2 = new java.math.BigDecimal(23.45d)  // violation
```

## Further Reading

* [CodeNarc - BigDecimalInstantiation](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#bigdecimalinstantiation-rule)