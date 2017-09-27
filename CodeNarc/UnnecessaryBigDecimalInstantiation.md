Pattern: Unnecessary `BigDecimal` instantiation

Issue: -

## Description

It is unnecessary to instantiate `BigDecimal` objects. Instead just use the decimal literal or the `G` identifier to force the type, such as `123.45` or `123.45G`.

This rule does not produce violations when the parameter evaluates to an integer/long, e.g. `new BigDecimal(42)`, `new BigDecimal(42L)` or `new BigDecimal("42")`, because using the "G" suffix on an integer value produces a `BigInteger`, rather than a `BigDecimal`, e.g. `45G`. So that means there is no way to produce a `BigDecimal` with exactly that value using a literal.

This rule also does not produce violations when the parameter is a double, e.g. `new BigDecimal(12.3)`.

## Further Reading

* [CodeNarc - UnnecessaryBigDecimalInstantiation](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryBigDecimalInstantiation)