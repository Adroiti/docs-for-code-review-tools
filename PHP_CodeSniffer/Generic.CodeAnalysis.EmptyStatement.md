Pattern: Empty statement

Issue: -

## Description

This sniff implements the common algorithm for empty statement body detection. A body is considered as empty if it is completely empty or it only contains whitespace characters and/or comments.

## Example

``` php
stmt {
  // foo
}
stmt (conditions) {
  // foo
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.EmptyStatement](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/EmptyStatementSniff.php)