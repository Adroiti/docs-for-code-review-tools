Pattern: Jumbled loop incrementer

Issue: -

## Description

To avoid confusion, incrementers in nested loops should use different variable names.

## Example

Example of **incorrect** code:

``` php
// $i is used in both loops
for ($i = 0; $i < 10; $i++) {
    for ($j = 0; $j < 10; $i++) {
		do_something($i, $j);
    }
}
```

Example of **correct** code:

```php
for ($i = 0; $i < 10; $i++) {
    for ($j = 0; $j < 10; $j++) {
		do_something($i, $j);
    }
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.JumbledIncrementer](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/JumbledIncrementerSniff.php)