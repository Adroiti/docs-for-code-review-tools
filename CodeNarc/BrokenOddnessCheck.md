Pattern: Broken oddness check

Issue: -

## Description

The code uses `x % 2 == 1` to check to see if a value is odd, but this won't work for negative numbers (e.g., `(-5) % 2 == -1)`. If this code is intending to check for oddness, consider using `x & 1 == 1`, or ` x % 2 != 0`.

Examples:

``` groovy
if (x % 2 == 1) { }             // violation
if (method() % 2 == 1) { }      // violation

if (x & 1 == 1) { }             // OK
if (x % 2 != 0) { }             // OK
```

## Further Reading

* [CodeNarc - BrokenOddnessCheck](http://codenarc.sourceforge.net/codenarc-rules-basic.html#BrokenOddnessCheck)