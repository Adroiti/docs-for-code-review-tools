Pattern: Unnecessary `exp % 1`

Issue: -

## Description

Any expression mod 1 (`exp % 1`) is guaranteed to always return zero. This code is probably an error, and should be either `exp & 1` or `exp % 2`.

Examples:

``` groovy
if (exp % 1) {}         // violation
if (method() % 1) {}    // violation

if (exp & 1) {}     // ok
if (exp % 2) {}     // ok
```

## Further Reading

* [CodeNarc - UnnecessaryModOne](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessarymodone-rule)