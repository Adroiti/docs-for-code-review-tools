Pattern: Malformed space around `foreach`

Issue: -

## Description

Verifies that `foreach` structures have the correct padding inside their bracketed statement.

## Configuration

By default, the rule ensures there are zero spaces following the opening bracket, and zero spaces preceding the closing bracket, as shown in the following code snippet:

```php
foreach ($foo as $bar) {
    // Body.
}
```

Another common way of padding control structures is to use a single space, as shown in the following code snippet:

```php
foreach ( $foo as $bar ) {
    // Body.
}
```

If you prefer to write your code like this, you can set the `requiredSpacesAfterOpen` and `requiredSpacesBeforeClose` properties to `1`, or whatever padding you prefer.

```xml
<rule ref="Squiz.ControlStructures.ForEachLoopDeclaration">
    <properties>
        <property name="requiredSpacesAfterOpen" value="1" />
        <property name="requiredSpacesBeforeClose" value="1" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.ControlStructures.ForEachLoopDeclaration](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/ControlStructures/ForEachLoopDeclarationSniff.php)