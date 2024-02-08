Pattern: Malformed multi-line assignment indentation

Issue: -

## Description

If an assignment goes over two lines, ensure the equal sign is indented.

## Configuration

By default, this rule ensures that the line with the assignment operator is indented 4 spaces, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="PEAR.Formatting.MultiLineAssignment">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - PEAR.Formatting.MultiLineAssignment](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/PEAR/Sniffs/Formatting/MultiLineAssignmentSniff.php)