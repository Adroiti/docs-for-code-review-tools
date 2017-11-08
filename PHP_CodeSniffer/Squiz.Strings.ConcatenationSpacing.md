Pattern: Malformed concatenation spacing

Issue: -

## Description

This rule enforces padding around concatenation operators.

## Configuration

By default, the rule ensures there are zero spaces before and after the concatenation operator, as shown in the following code snippet:

```php
$foo = $number.'-'.$letter;
```

Another common way of padding concatenation operators is to use a single space, as shown in the following code snippet:

```php
$foo = $number . '-' . $letter;
```

If you prefer to write your code like this, you can set the `spacing` property to `1`, or whatever padding you prefer.

```xml
<rule ref="Squiz.Strings.ConcatenationSpacing">
    <properties>
        <property name="spacing" value="1" />
    </properties>
</rule>
```

Sometimes long concatenation statements are broken over multiple lines to work within a maximum line length, but this rule will generate an error for these cases by default. Setting the `ignoreNewlines` property to `true` will allow newline characters before or after a concatenation operator, and any required padding for alignment.

```xml
<rule ref="Squiz.Strings.ConcatenationSpacing">
    <properties>
        <property name="ignoreNewlines" value="true" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.Strings.ConcatenationSpacing](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/Strings/ConcatenationSpacingSniff.php)