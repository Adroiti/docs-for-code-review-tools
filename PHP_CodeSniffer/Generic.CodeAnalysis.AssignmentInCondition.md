Pattern: Assignment in condition

Issue: -

## Description

Assignments in conditionals are often typos: for example `if (var1 = var2)` instead of `if (var1 == var2)`. They also can be an indicator of overly clever code which decreases maintainability.

## Example

Example of **incorrect** code:

``` php
if ($test = 'abc') {
    do_something();
}
```

Example of **correct** code:

```php
if ($test === 'abc') {
    do_something();
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.AssignmentInCondition](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/AssignmentInConditionSniff.php)