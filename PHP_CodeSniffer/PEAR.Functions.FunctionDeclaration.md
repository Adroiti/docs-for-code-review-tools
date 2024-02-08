Pattern: Invalid function declaration

Issue: -

## Description

Ensure single and multi-line function declarations are defined correctly.

## Configuration

By default, this rule ensures that each line is indented 4 spaces, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="PEAR.Functions.FunctionDeclaration">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - PEAR.Functions.FunctionDeclaration](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/PEAR/Sniffs/Functions/FunctionDeclarationSniff.php)