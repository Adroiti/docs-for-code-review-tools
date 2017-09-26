Pattern: Use of ternary instead of *Elvis* expression

Issue: -

## Description

Checks for ternary expressions where the *boolean* and *true* expressions are the same. These can be simplified to an *Elvis* expression.

Example of violations:

``` groovy
x ? x : false               // violation; can simplify to x ?: false

foo() ? foo() : bar()       // violation; can simplify to foo() ?: bar()
foo(1) ? foo(1) : 123       // violation; can simplify to foo(1) ?: 123

(x == y) ? same : diff      // OK
x ? y : z                   // OK
x ? x + 1 : x + 2           // OK
x ? 1 : 0                   // OK
x ? !x : x                  // OK
!x ? x : null               // OK

foo() ? bar() : 123         // OK
foo() ? foo(99) : 123       // OK
foo(x) ? foo() : 123        // OK
foo(1) ? foo(2) : 123       // OK
```

NOTE: If the *boolean* and *true* expressions are the same method call, and that method call has *side-effects*, then converting it to a *Elvis* expression may produce *different* behavior. The method will only be called *once*, rather than *twice*. But relying on those *side-effects* as part of a ternary expression behavior is confusing, error-prone and just a bad idea. In any case, that code should be refactored to move the reliance on the side-effects out of the ternary expression.

## Further Reading

* [CodeNarc - TernaryCouldBeElvis](http://codenarc.sourceforge.net/codenarc-rules-convention.html#TernaryCouldBeElvis)