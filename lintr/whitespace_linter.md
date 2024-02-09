Pattern: Inconsistent indentation

Issue: -

## Description

Checks that the correct character is used for indentation.

Example of **incorrect** code:

```r
lint(
  text = "\tx",
  linters = whitespace_linter()
)
#> ::warning file=<text>,line=1,col=1::file=<text>,line=1,col=1,[whitespace_linter] Use spaces to indent, not tabs.

```

Example of **correct** code:

```r
lint(
  text = "  x",
  linters = whitespace_linter()
)
```

## Further Reading

* [lintr - Available linters](https://lintr.r-lib.org/reference/index.html)