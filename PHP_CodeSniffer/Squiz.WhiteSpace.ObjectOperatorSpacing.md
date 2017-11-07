Pattern: Malformed object operator spacing

Issue: -

## Description

This rule ensures there are no spaces surrounding an object operator. 

# Configuration

Sometimes long object chains are broken over multiple lines to work within a maximum line length, but this rule will generate an error for these cases by default. Setting the `ignoreNewlines` property to `true` will allow newline characters before or after an object operator, and any required padding for alignment.

```xml
<rule ref="Squiz.WhiteSpace.ObjectOperatorSpacing">
    <properties>
        <property name="ignoreNewlines" value="true" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.WhiteSpace.ObjectOperatorSpacing](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/WhiteSpace/ObjectOperatorSpacingSniff.php)