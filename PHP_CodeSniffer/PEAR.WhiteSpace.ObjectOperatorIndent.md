Pattern: Malformed object operator indentation

Issue: -

## Description

Checks that object operators are indented correctly.

## Configuration

By default, this rule ensures that each line is indented 4 spaces, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="PEAR.WhiteSpace.ObjectOperatorIndent">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - PEAR.WhiteSpace.ObjectOperatorIndent](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/PEAR/Sniffs/WhiteSpace/ObjectOperatorIndentSniff.php)