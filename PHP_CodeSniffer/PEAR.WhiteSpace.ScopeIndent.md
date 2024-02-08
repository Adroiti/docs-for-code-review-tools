Pattern: Malformed indentation

Issue: -

## Description

Checks that control structures are structured and indented correctly.

## Configuration

```xml
<!-- Tabs should represent 4 spaces. -->
<arg name="tab-width" value="4"/>


<rule ref="PEAR.WhiteSpace.ScopeIndent">
    <properties>
        <property name="exact" value="true" />
        <property name="tabIndent" value="true" />
        <property name="ignoreIndentationTokens" type="array"
            value="T_COMMENT,T_DOC_COMMENT_OPEN_TAG"/>
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - PEAR.WhiteSpace.ScopeIndent](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/PEAR/Sniffs/WhiteSpace/ScopeIndentSniff.php)