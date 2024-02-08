Pattern: Invalid end of line character

Issue: -

## Description

This rule ensures that files use a specific line ending, which can be customised by setting the `eolChar` property.

## Configuration

```xml
<rule ref="Generic.Files.LineEndings">
    <properties>
        <property name="eolChar" value="\r\n" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Generic.Files.LineEndings](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/Files/LineEndingsSniff.php)