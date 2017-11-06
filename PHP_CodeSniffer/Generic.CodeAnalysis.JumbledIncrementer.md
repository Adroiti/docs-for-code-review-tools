Pattern: Jumbled loop incrementor

Issue: -

## Description

Detects the usage of one and the same incrementor in an outer and an inner loop. This is confusing and should be avoided.

## Example

``` php
class Foo
{
    public function bar($x)
    {
        for ($i = 0; $i < 10; $i++)
        {
            for ($k = 0; $k < 20; $i++)
            {
                echo 'Hello';
            }
        }
    }
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.JumbledIncrementer](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/JumbledIncrementerSniff.php)