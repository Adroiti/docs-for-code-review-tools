Pattern: Use of `if` instead of *Elvis* expression

Issue: -

## Description

Catch an `if` block that could be written as an elvis expression.

Example of violations:

``` groovy
if (!x) {                   // violation
    x = 'some value'
}

if (!x)                     // violation
    x = "some value"

if (!params.max) {          // violation
  params.max = 10
}

x ?: 'some value'           // OK
```

## Further Reading

* [CodeNarc - CouldBeElvis](http://codenarc.sourceforge.net/codenarc-rules-convention.html#CouldBeElvis)