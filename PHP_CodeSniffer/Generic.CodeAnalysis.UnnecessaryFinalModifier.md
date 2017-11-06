Pattern: Unnecessary `final` modifier

Issue: -

## Description

Detects unnecessary final modifiers inside of final classes.

## Example

``` php
final class Foo
{
    public final function bar()
    {
    }
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.UnnecessaryFinalModifier](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/UnnecessaryFinalModifierSniff.php)