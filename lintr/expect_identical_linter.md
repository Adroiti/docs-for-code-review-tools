Pattern: Missing use of `expect_identical(x, y)`

Issue: -

## Description

Enforces the usage of `testthat::expect_identical()` as the default expectation for comparisons in a testthat suite. `expect_true(identical(x, y))` is an equivalent but unadvised method of the same test. 

## Examples

```r
# will produce lints
lint(
  text = "expect_equal(x, y)",
  linters = expect_identical_linter()
)

# okay
lint(
  text = "expect_identical(x, y)",
  linters = expect_identical_linter()
)
```

## Further Reading

* [lintr - expect_identical_linter](https://lintr.r-lib.org/reference/expect_identical_linter.html)