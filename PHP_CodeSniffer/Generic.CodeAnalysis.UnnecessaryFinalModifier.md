Pattern: Unnecessary `final` modifier

Issue: -

## Description

Detects unnecessary final modifiers inside of final classes.

## Example

Example of **incorrect** code:

```php
final class SomeClass
{
    public final function some_method()
    {
    }
}
```

Example of **correct** code:

```php
final class SomeClass
{
    public function some_method()
    {
    }
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.UnnecessaryFinalModifier](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/UnnecessaryFinalModifierSniff.php)