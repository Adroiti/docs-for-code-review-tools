Pattern: Unnecessary whitespace

Issue: -

## Description

This rule enforces that there should not be whitespace at the end of a line, and that functions should not contain multiple blank lines in a row. 

## Configuration

If the `ignoreBlankLines` property is set to `true`, blank lines (lines that contain only whitespace) may have spaces and tabs as their content, and multiple blank lines will be allows inside functions.

```xml
<rule ref="Squiz.WhiteSpace.SuperfluousWhitespace">
    <properties>
        <property name="ignoreBlankLines" value="true" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.WhiteSpace.SuperfluousWhitespace](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/WhiteSpace/SuperfluousWhitespaceSniff.php)