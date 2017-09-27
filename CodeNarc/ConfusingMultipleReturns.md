Pattern: Confusing multiple returns

Issue: -

## Description

Multiple return values can be used to set several variables at once. To use multiple return values, the left hand side of the assignment must be enclosed in parenthesis. If not, then you are not using multiple return values, you're only assigning the last element.

Example of violations:

``` groovy
def a, b = [1, 2] // bad, b is null
def c, d, e = [1, 2, 3] // bad, c and d are null
class SomeClass {
def a, b, c = [1, 2, 3]  // bad, a and b are null
}

def x = 1              // ok
def (f, g) = [1, 2]    // ok
(a, b, c) = [1, 2, 3]  // ok
```

## Further Reading

* [CodeNarc - ConfusingMultipleReturns](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ConfusingMultipleReturns)