Pattern: Malformed end comment for long condition

Issue: -

## Description

Ensures long conditions have a comment at the end.

## Configuration

The `lineLimit` property allows you to configure the numbers of lines that the code block must span before requiring a comment. By default, the code block must be at least 20 lines long, including the opening and closing lines, but you can change the required length by setting the `lineLimit` property.

```xml
<rule ref="Squiz.Commenting.LongConditionClosingComment">
    <properties>
        <property name="lineLimit" value="40" />
    </properties>
</rule>
```

When a closing comment is required, the format defaults to `//end %s`, where the `%s` placeholder is replaced with the type of the code block. For example, `//end if`, `//end foreach`, or `//end switch`. You can change the format of the end comment by setting the `commentFormat` property.

```xml
<!-- Have code block comments look like // end foreach() etc. -->
<rule ref="Squiz.Commenting.LongConditionClosingComment">
    <properties>
        <property name="commentFormat" value="// end %s()" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.Commenting.LongConditionClosingComment](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/Commenting/LongConditionClosingCommentSniff.php)