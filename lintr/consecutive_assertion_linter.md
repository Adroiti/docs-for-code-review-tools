Pattern: Redundant consecutive calls to assertions

Issue: -

## Description

`stopifnot(`) accepts any number of tests, so sequences like `stopifnot(x); stopifnot(y)` are redundant. Ditto for tests using `assertthat::assert_that()` without specifying `msg=`.

## Examples

```r
# will produce lints
lint(
  text = "stopifnot(x); stopifnot(y)",
  linters = consecutive_assertion_linter()
)

# okay
lint(
  text = "stopifnot(x, y)",
  linters = consecutive_assertion_linter()
)
```

## Further Reading

* [lintr - Available linters](https://lintr.r-lib.org/reference/index.html)