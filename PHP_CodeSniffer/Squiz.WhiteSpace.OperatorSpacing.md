Pattern: Malformed operator spacing

Issue: -

## Description

Verifies that operators have valid spacing surrounding them.

# Configuration

Sometimes long statements are broken over multiple lines to work within a maximum line length, but this rule will generate an error for these cases by default. Setting the `ignoreNewlines` property to `true` will allow newline characters before or after an operator, and any required padding for alignment.

```xml
<rule ref="Squiz.WhiteSpace.OperatorSpacing">
    <properties>
        <property name="ignoreNewlines" value="true" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.WhiteSpace.OperatorSpacing](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/WhiteSpace/OperatorSpacingSniff.php)