Pattern: Malformed alignment of assignment

Issue: -

## Description

This rule checks the alignment of assignment operators. If there are multiple adjacent assignments, it checks that the equals signs of each assignment are aligned.

## Configuration

The difference in alignment between two adjacent assignments is occasionally quite large, so aligning equals signs would create extremely long lines. By setting the `maxPadding` property, you can configure the maximum amount of padding required to align the assignment with the surrounding assignments before the alignment is ignored and no warnings will be generated.

```xml
<rule ref="Generic.Formatting.MultipleStatementAlignment">
    <properties>
        <property name="maxPadding" value="50" />
    </properties>
</rule>
```

If the `error` property is set to `true`, an error will be thrown for violations instead of a warning.

```xml
<rule ref="Generic.Formatting.MultipleStatementAlignment">
    <properties>
        <property name="error" value="true" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Generic.Formatting.MultipleStatementAlignment](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/Formatting/MultipleStatementAlignmentSniff.php)