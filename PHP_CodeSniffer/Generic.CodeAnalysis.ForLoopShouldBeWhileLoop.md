Pattern: Use of `for` instead of `while` loop

Issue: -

## Description

Detects `for` loops that can be simplified as a `while` loop.

## Example

``` php
class Foo
{
    public function bar($x)
    {
        for (;true;) true; // No Init or Update part, may as well be: while (true)
    }
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.ForLoopShouldBeWhileLoop](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/ForLoopShouldBeWhileLoopSniff.php)