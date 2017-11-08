Pattern: Unnecessary string concatenation

Issue: -

## Description

Catches concatenation of two string literals on the same line. These can be safely joined.

## Example

Example of **incorrect** code:

``` php
echo '/..' . '/path/to/file.php';
```

Example of **correct** code:

```php
echo '/../path/to/file.php';
```

# Configuration

Sometimes long strings are broken over multiple lines to work within a maximum line length, but this rule will generate an error for these cases by default. Setting the `allowMultiline` property to `true` will get the rule to allow string concatenation if the string covers multiple lines.

```xml
<rule ref="Generic.Strings.UnnecessaryStringConcat">
    <properties>
        <property name="allowMultiline" value="true" />
    </properties>
</rule>
```

If the `error` property is set to `false`, a warning will be thrown for violations instead of an error.

```xml
<rule ref="Generic.Strings.UnnecessaryStringConcat">
    <properties>
        <property name="error" value="false" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Generic.Strings.UnnecessaryStringConcat](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/Strings/UnnecessaryStringConcatSniff.php)