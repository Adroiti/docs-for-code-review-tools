Pattern: Malformed control statement

Issue: -

## Description

Verifies that control structures match a specific pattern of whitespace and bracket placement. 

## Configuration

By default, comments placed within the declaration will generate an error, but the rule can be told to ignore comments by setting the `ignoreComments` property to `true`.

```xml
<rule ref="PEAR.ControlStructures.ControlSignature">
    <properties>
        <property name="ignoreComments" value="false" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - PEAR.ControlStructures.ControlSignature](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/PEAR/Sniffs/ControlStructures/ControlSignatureSniff.php)