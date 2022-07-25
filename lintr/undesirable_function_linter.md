Pattern: Use of undesirable function

Issue: -

## Description

Avoid functions that return different types of output.  E.g. `sapply` is not type safe, it returns a different data type depending on the input, and on the input length. In particular:

```r
sapply(1:10, paste)
```

returns a character vector, and

```r
sapply(integer(), paste)
```

returns a list. This often leads to errors in edge cases. A better alternative is `vapply`.


Avoid functions that change global state: `setwd()`, `options()`, `par()`, `sink()`.

## Further Reading

* [lintr - Available linters](https://lintr.r-lib.org/reference/index.html)