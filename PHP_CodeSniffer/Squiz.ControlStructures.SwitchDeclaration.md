Pattern: Malformed `switch` declaration

Issue: -

## Description

Enforces `switch` statement formatting.

## Configuration

By default, this rule ensures that the keywords are indented 4 spaces from the `switch` keyword and that the terminating statement is indented 4 spaces from the `case` or `default` keyword, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="Squiz.ControlStructures.SwitchDeclaration">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.ControlStructures.SwitchDeclaration](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/ControlStructures/SwitchDeclarationSniff.php)