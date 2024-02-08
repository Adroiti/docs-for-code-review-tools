Pattern: Commented out code

Issue: -

## Description

Warns about commented out code.

## Configuration

By default, a warning is generated if a comment appears to be more than 35% valid code. If you find that the rule is generating a lot of false positives, you may want to raise the valid code threshold by increasing the `maxPercentage` property. Similarly, if you find that the rule is generating a lot of false negatives, you may want to make it more sensitive by dropping the threshold by decreasing the `maxPercentage` property.

```xml
<!-- Make this rule more sensitive to commented out code blocks. -->
<rule ref="Squiz.PHP.CommentedOutCode">
    <properties>
        <property name="maxPercentage" value="20" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.PHP.CommentedOutCode](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/PHP/CommentedOutCodeSniff.php)