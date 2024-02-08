Pattern: Malformed closing brace indentation

Issue: -

## Description

Checks that the closing braces of scopes are aligned correctly.

## Configuration

By default, this rule ensures that the statement is indented 4 spaces from the `case` or `default` keyword, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="PEAR.WhiteSpace.ScopeClosingBrace">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - PEAR.WhiteSpace.ScopeClosingBrace](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/PEAR/Sniffs/WhiteSpace/ScopeClosingBraceSniff.php)