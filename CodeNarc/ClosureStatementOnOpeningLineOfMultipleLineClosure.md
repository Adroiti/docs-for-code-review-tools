Pattern: Closure statement on opening line of multiple line closure

Issue: -

## Description

Checks for closure logic on first line (after `->`) for a multi-line closure. That breaks the symmetry of indentation (if the subsequent statements are indented normally), and that first statement can be easily missed when reading the code.

Example of violations:

``` groovy
def closure = { name -> println name
    addToCounts()
    println “done” }
```

## Further Reading

* [CodeNarc - ClosureStatementOnOpeningLineOfMultipleLineClosure](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#closurestatementonopeninglineofmultiplelineclosure-rule)