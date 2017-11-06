Pattern: Nesting depth is too high

Issue: -

## Description

This rule checks how many level deep that code is nested within a function.

## Configuration

* `nestingLevel` : the nesting level above which this sniff will generate warnings
* `absoluteNestingLevel` : the nesting level above which this sniff will generate errors

```xml
<rule ref="Generic.Metrics.NestingLevel">
    <properties>
        <property name="nestingLevel" value="8" />
        <property name="absoluteNestingLevel" value="12" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Generic.Metrics.NestingLevel](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/Metrics/NestingLevelSniff.php)