Pattern: Invalid function call signature

Issue: -

## Description

Ensures function calls are formatted correctly.

## Configuration

By default, the rule ensures there are zero spaces following the opening bracket, and zero spaces preceding the closing bracket, as shown in the following code snippet:

```php
$foo = getValue($a, $b, $c);
```

Another common way of padding function calls is to use a single space, as shown in the following code snippet:

```php
$foo = getValue( $a, $b, $c );
```

If you prefer to write your code like this, you can set the `requiredSpacesAfterOpen` and `requiredSpacesBeforeClose` properties to `1`, or whatever padding you prefer.

```xml
<rule ref="PEAR.Functions.FunctionCallSignature">
    <properties>
        <property name="requiredSpacesAfterOpen" value="1" />
        <property name="requiredSpacesBeforeClose" value="1" />
    </properties>
</rule>
```

This rule also enforces the formatting of multi-line function calls. By default, multiple arguments can appear on each line, as shown in the following code snippet:

```php
$returnValue = foo(
    $a, $b, $c,
    $d, $e
);
```

Another common way of defining multi-line function calls is to have one argument per line, as shown in the following code snippet:

```php
$returnValue = foo(
    $a,
    $b,
    $c,
    $d,
    $e
);
```

If you prefer to write your code like this, you can set the `allowMultipleArguments` property to `false`.

```xml
<rule ref="PEAR.Functions.FunctionCallSignature">
    <properties>
        <property name="allowMultipleArguments" value="false" />
    </properties>
</rule>
```

By default, this rule ensures that each line in a multi-line function call is indented 4 spaces, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="PEAR.Functions.FunctionCallSignature">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - PEAR.Functions.FunctionCallSignature](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/PEAR/Sniffs/Functions/FunctionCallSignatureSniff.php)