Pattern: Use of inline control structure

Issue: -

## Description

Verifies that inline control statements are not present.

## Configuration

If the `error` property is set to `false`, a warning will be thrown for violations instead of an error.

```xml
<rule ref="Generic.ControlStructures.InlineControlStructure">
    <properties>
        <property name="error" value="false" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Generic.ControlStructures.InlineControlStructure](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/ControlStructures/InlineControlStructureSniff.php)