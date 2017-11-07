Pattern: Malformed control statement

Issue: -

## Description

Verifies that control statements conform to their coding standards.

## Configuration

By default, the rule ensures there is one space before the opening brace for control structures using standard syntax, and one space before the colon for control structures using alternative syntax, as shown in the following code snippet:

```php
if ($foo) :
    // IF body.
else :
    // ELSE body.
endif;
```

A common way of defining control structures using alternative syntax is to put no padding before the colon, as shown in the following code snippet:

```php
if ($foo):
    // IF body.
else:
    // ELSE body.
endif;
```

If you prefer to write your code like this, you can set the `requiredSpacesBeforeColon` property to `0`.

```xml
<rule ref="Squiz.ControlStructures.ControlSignature">
    <properties>
        <property name="requiredSpacesBeforeColon" value="0" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.ControlStructures.ControlSignature](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/ControlStructures/ControlSignatureSniff.php)