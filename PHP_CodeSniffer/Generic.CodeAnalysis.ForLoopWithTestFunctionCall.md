Pattern: `for` with test function call

Issue: -

## Description

Detects `for` loops that use a function call in the test expression.

## Example

``` php
class Foo
{
    public function bar($x)
    {
        $a = array(1, 2, 3, 4);
        for ($i = 0; $i < count($a); $i++) {
             $a[$i] *= $i;
        }
    }
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.ForLoopWithTestFunctionCall](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/ForLoopWithTestFunctionCallSniff.php)