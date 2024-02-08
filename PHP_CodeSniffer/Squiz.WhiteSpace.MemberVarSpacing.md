Pattern: Malformed class member spacing

Issue: -

## Description

Verifies that class members are spaced correctly.

## Configuration

This rule checks that there is one blank line before between member vars and before the fist member var, but you can change the required padding using the `spacing` and `spacingBeforeFirst` properties.

```xml
<!--
 Ensure 2 blank lines between member vars,
 but don't require blank lines before the first.
-->
<rule ref="Squiz.WhiteSpace.MemberVarSpacing">
    <properties>
        <property name="spacing" value="2" />
        <property name="spacingBeforeFirst" value="0" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.WhiteSpace.MemberVarSpacing](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/WhiteSpace/MemberVarSpacingSniff.php)