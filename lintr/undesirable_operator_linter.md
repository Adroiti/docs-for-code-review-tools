Pattern: Use of undesirable operator

Issue: -

## Description

It is typically a design mistake to use `:::` in your code since the corresponding object has probably been kept internal for a good reason. Consider contacting the package maintainer if you feel the need to access the object for anything but mere inspection.

The good use of `<<-`/`->>` operator is in conjuction with lexical scope, where an environment stores state for a function or set of functions that modify the state by using superassignment. Otherwise it can become problematic as it modifies variables in the global environment.

## Further Reading

* [lintr - Available linters](https://lintr.r-lib.org/reference/index.html)