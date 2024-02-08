Pattern: Empty statement

Issue: -

## Description

This rule implements the common algorithm for empty statement body detection. A body is considered as empty if it is completely empty or it only contains whitespace characters and/or comments.

## Example

Example of **incorrect** code:

``` php
if ($test) {
    // do nothing
}
```

Example of **correct** code:

```php
if ($test) {
    $var = 1;
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.EmptyStatement](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/EmptyStatementSniff.php)