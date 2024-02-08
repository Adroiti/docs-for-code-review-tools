Pattern: Line is too long

Issue: -

## Description

Your source code should not contain very long lines. The default wrapping in most tools disrupts the visual structure of the code, making it more difficult to understand.

## Configuration

This rule checks all lines in a file and generates warnings if they are over `lineLimit` characters in length and errors if they are over `absoluteLineLimit` in length. These properties can be used to set the threshold at which errors are reported.

> Note: The value of the `lineLimit` property should be less than or equal to the value of the `absoluteLineLimit` property.

```xml
<!--
 Warn about lines longer than 100 chars,
 and error for lines longer than 135 chars.
-->
<rule ref="Generic.Files.LineLength">
    <properties>
        <property name="lineLimit" value="100" />
        <property name="absoluteLineLimit" value="135" />
    </properties>
</rule>
```

If errors are not required, the value of `absoluteLineLimit` can be set to zero.

```xml
<!-- Warn about lines longer than 135 chars, and never error. -->
<rule ref="Generic.Files.LineLength">
    <properties>
        <property name="lineLimit" value="135" />
        <property name="absoluteLineLimit" value="0" />
    </properties>
</rule>
```

If the `ignoreComments` property is set to `true`, no error or warning will be thrown for a line that only contains a comment, no matter how long the line is.

```xml
<rule ref="Generic.Files.LineLength">
    <properties>
        <property name="ignoreComments" value="true" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Generic.Files.LineLength](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/Files/LineLengthSniff.php)