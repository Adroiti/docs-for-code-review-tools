Pattern: Malformed function name

Issue: -

## Description

Ensures method and functions are named in _CamelCaps_.

## Configuration

Strictly speaking, a name cannot have two capital letters next to each other in CamelCaps format. By setting the `strict` property to `false`, the rule is more lenient and allows for two capital letters next to each other in function and method names.

```xml
<rule ref="Generic.NamingConventions.CamelCapsFunctionName">
    <properties>
        <property name="strict" value="false" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Generic.NamingConventions.CamelCapsFunctionName](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/NamingConventions/CamelCapsFunctionNameSniff.php)