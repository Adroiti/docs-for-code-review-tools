Pattern: Use of `testthat::expect_true()`

Issue: -

## Description

`testthat::expect_gt()`, `testthat::expect_gte()`, `testthat::expect_lt()`, `testthat::expect_lte()`, and `testthat::expect_equal()` exist specifically for testing comparisons between two objects. 

`testthat::expect_true()` can also be used for such tests, but it is better to use the tailored function instead. 

## Examples

```r
# will produce lints
lint(
  text = "expect_true(x > y)",
  linters = expect_comparison_linter()
)

# okay
lint(
  text = "expect_gt(x, y)",
  linters = expect_comparison_linter()
)
```

## Further Reading

* [lintr - expect_comparison_linter](https://lintr.r-lib.org/reference/expect_comparison_linter.html)