Pattern: Unconditional `if` statement

Issue: -

## Description

Detects statement conditions that are only set to one of the constant values: **true** or **false**.

## Example

``` php
class Foo
{
    public function close()
    {
        if (true)
        {
            // ...
        }
    }
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.UnconditionalIfStatement](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/UnconditionalIfStatementSniff.php)