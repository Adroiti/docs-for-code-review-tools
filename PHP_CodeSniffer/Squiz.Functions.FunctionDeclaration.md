Pattern: Malformed function declaration

Issue: -

## Description

Checks that function declarations match a specific pattern of whitespace and bracket placement.

## Configuration

By default, comments placed within the function declaration will generate an error, but the rule can be told to ignore comments by setting the `ignoreComments` property to `true`.

```xml
<rule ref="Squiz.Functions.FunctionDeclaration">
    <properties>
        <property name="ignoreComments" value="false" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.Functions.FunctionDeclaration](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/Functions/FunctionDeclarationSniff.php)