Pattern: Malformed function spacing

Issue: -

## Description

This rule enforces separation between methods in a class or interface.

# Configuration

By default, this rule checks that there are two blank lines before and after functions declarations, but you can change the required padding using the `spacing` property.

```xml
<!-- Ensure 1 blank line before and after functions. -->
<rule ref="Squiz.WhiteSpace.FunctionSpacing">
    <properties>
        <property name="spacing" value="1" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.WhiteSpace.FunctionSpacing](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/WhiteSpace/FunctionSpacingSniff.php)