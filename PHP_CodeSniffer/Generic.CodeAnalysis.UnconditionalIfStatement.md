Pattern: Constant `if` statement

Issue: -

## Description

If statements that are always evaluated should be simplified or avoided altogether.

## Example

Example of **incorrect** code:

```php
if (true) {
    $var = 1;
}
```

Example of **correct** code:

```php
if ($test) {
    $var = 1;
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.UnconditionalIfStatement](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/UnconditionalIfStatementSniff.php)