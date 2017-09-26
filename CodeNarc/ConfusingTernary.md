Pattern: Confusing ternary

Issue: -

## Description

In a ternary expression avoid negation in the test. For example, rephrase: `(x != y) ? diff : same` as: `(x == y) ? same : diff`. Consistent use of this rule makes the code easier to read. Also, this resolves trivial ordering problems, such as "does the error case go first?" or "does the common case go first?".

Example:

``` groovy
(x != y) ? diff : same      // triggers violation
(!x) ? diff : same          // triggers violation

(x == y) ? same : diff      // OK
(x) ? same : diff           // OK

// this is OK, because of GroovyTruth there is no inverse of != null
(x != null) ? diff : same

// this is OK, because of GroovyTruth there is no inverse of != true
(x != true) ? diff : same

// this is OK, because of GroovyTruth there is no inverse of != false
(x != false) ? diff : same
```

## Further Reading

* [CodeNarc - ConfusingTernary](http://codenarc.sourceforge.net/codenarc-rules-convention.html#ConfusingTernary)