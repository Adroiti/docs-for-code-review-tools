Pattern: Use of alias function

Issue: -

## Description

This rule discourages the use of alias functions that are kept in PHP for compatibility with older versions. 

## Configuration

Rule can be used to forbid the use of any function by setting the `forbiddenFunctions` property. The property is defined as an array, with the keys being the names of the functions to forbid and the values being the names of suggested alternative functions to use instead. If no alternative function exists (i.e., the function should never be used) specify `null` as the value.

```xml
<rule ref="Generic.PHP.ForbiddenFunctions">
    <properties>
        <property name="forbiddenFunctions" type="array"
            value="print=>echo,create_function=>null" />
     </properties>
</rule>
```

If the `error` property is set to `false`, a warning will be thrown for violations instead of an error.

```xml
<rule ref="Generic.PHP.ForbiddenFunctions">
    <properties>
        <property name="error" value="false" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Generic.PHP.ForbiddenFunctions](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/PHP/ForbiddenFunctionsSniff.php)