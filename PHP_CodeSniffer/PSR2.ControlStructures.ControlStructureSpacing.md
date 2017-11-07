Pattern: Malformed control structure spacing

Issue: -

## Description

Checks that control structures have the correct spacing around brackets.

## Configuration

By default, the rule ensures there are zero spaces following the opening bracket, and zero spaces preceding the closing bracket, as shown in the following code snippet:

```php
if ($condition === true) {
    // Body.
}
```

Another common way of padding control structures is to use a single space, as shown in the following code snippet:

```php
if ( $condition === true ) {
    // Body.
}
```

If you prefer to write your code like this, you can set the `requiredSpacesAfterOpen` and `requiredSpacesBeforeClose` properties to `1`, or whatever padding you prefer.

```xml
<rule ref="PSR2.ControlStructures.ControlStructureSpacing">
    <properties>
        <property name="requiredSpacesAfterOpen" value="1" />
        <property name="requiredSpacesBeforeClose" value="1" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - PSR2.ControlStructures.ControlStructureSpacing](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/PSR2/Sniffs/ControlStructures/ControlStructureSpacingSniff.php)