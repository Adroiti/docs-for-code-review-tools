Pattern: Malformed multi-line `if` condition

Issue: -

## Description

Ensure multi-line `if` conditions are defined correctly.

## Configuration

By default, this rule ensures that each line of the condition is indented 4 spaces, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="PEAR.ControlStructures.MultiLineCondition">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - PEAR.ControlStructures.MultiLineCondition](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/PEAR/Sniffs/ControlStructures/MultiLineConditionSniff.php)