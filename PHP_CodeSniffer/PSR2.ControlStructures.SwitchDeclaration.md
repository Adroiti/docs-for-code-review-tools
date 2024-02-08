Pattern: Malformed `switch` declaration

Issue: -

## Description

Ensures all `switch` statements are defined correctly.

## Configuration

By default, this rule ensures that the statement is indented 4 spaces from the `case` or `default` keyword, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="PSR2.ControlStructures.SwitchDeclaration">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - PSR2.ControlStructures.SwitchDeclaration](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/PSR2/Sniffs/ControlStructures/SwitchDeclarationSniff.php)