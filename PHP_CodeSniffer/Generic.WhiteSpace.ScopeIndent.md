Pattern: Malformed indentation

Issue: -

## Description

This rule checks that code blocks are indented correctly. 

## Configuration

By default, this rule ensures that code blocks are indented 4 spaces, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="Generic.WhiteSpace.ScopeIndent">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

The `exact` property is used to determine whether an indent is treated as an exact number or as a minimum amount. By default, code blocks must be indented at least `indent` spaces from the last code block. If `exact` is set to `true`, code blocks must be indented exactly `indent` spaces from the last code block.

```xml
<rule ref="Generic.WhiteSpace.ScopeIndent">
    <properties>
        <property name="exact" value="true" />
    </properties>
</rule>
```

By default, this rule enforces the use of spaces for indentation and also uses spaces when fixing the indentation of code blocks. If you prefer using tabs, you can set the `tabIndent` property to `true`. 

```xml
<!-- Tabs should represent 4 spaces. -->
<arg name="tab-width" value="4"/>
...
<!-- Indent using tabs. -->
<rule ref="Generic.WhiteSpace.ScopeIndent">
    <properties>
        <property name="tabIndent" value="true" />
    </properties>
</rule>
```

Setting the `ignoreIndentationTokens` property provides the rule with a list of tokens that do not need to be checked for indentation. This is commonly used to ignore indentation for code structures such as comments and here/nowdocs.

```xml
<rule ref="Generic.WhiteSpace.ScopeIndent">
    <properties>
        <property name="ignoreIndentationTokens" type="array"
            value="T_COMMENT,T_DOC_COMMENT_OPEN_TAG"/>
    </properties>
</rule>
```

## Further Reading

* [PHP_Coderuleer - Generic.WhiteSpace.ScopeIndent](https://github.com/squizlabs/PHP_Coderuleer/blob/master/src/Standards/Generic/rules/WhiteSpace/ScopeIndentrule.php)