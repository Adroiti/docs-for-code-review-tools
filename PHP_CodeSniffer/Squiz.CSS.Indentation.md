Pattern: Malformed style indentation

Issue: -

## Description

Checks the indentation of CSS class definitions. 

# Configuration

By default, this rule ensures that style statements are indented using 4 spaces, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="Squiz.CSS.Indentation">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.CSS.Indentation](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/CSS/IndentationSniff.php)