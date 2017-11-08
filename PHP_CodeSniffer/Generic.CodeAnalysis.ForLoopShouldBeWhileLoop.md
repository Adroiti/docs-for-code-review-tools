Pattern: Use of `for` instead of `while` loop

Issue: -

## Description

Detects `for` loops that can be simplified as a `while` loop.

## Example

Example of **incorrect** code:

``` php
// no Init or Update part
for (;$test;) {
    $test = doSomething();
}
```

Example of **correct** code:

```php
for ($i = 0; $i < 10; $i++) {
    echo "{$i}\n";
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.ForLoopShouldBeWhileLoop](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/ForLoopShouldBeWhileLoopSniff.php)