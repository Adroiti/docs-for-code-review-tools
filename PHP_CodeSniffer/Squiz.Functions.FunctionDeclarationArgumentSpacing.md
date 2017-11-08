Pattern: Malformed function argument spacing

Issue: -

## Description

Checks that arguments in function declarations are spaced correctly.

## Configuration

By default, the rule ensures there are zero spaces before and after the equals sign, as shown in the following code snippet:

```php
function foo($a='a', $b='b') {
    // Body.
}
```

Another common way of defining default values is to use a single space, as shown in the following code snippet:

```php
function foo($a = 'a', $b = 'b') {
    // Body.
}
```

If you prefer to write your code like this, you can set the `equalsSpacing` property to `1`, or whatever padding you prefer.

```xml
<rule ref="Squiz.Functions.FunctionDeclarationArgumentSpacing">
    <properties>
        <property name="equalsSpacing" value="1" />
    </properties>
</rule>
```

Another of the rules this rule enforces is that functions have the correct padding inside their bracketed list of arguments. By default, the rule ensures there are zero spaces following the opening bracket, and zero spaces preceding the closing bracket, as shown in the following code snippet:

```php
function foo($a, $b) {
    // Body.
}
```

Another common way of padding argument lists is to use a single space, as shown in the following code snippet:

```php
function foo( $a, $b ) {
    // Body.
}
```

If you prefer to write your code like this, you can set the `requiredSpacesAfterOpen` and `requiredSpacesBeforeClose` properties to `1`, or whatever padding you prefer.

```xml
<rule ref="Squiz.Functions.FunctionDeclarationArgumentSpacing">
    <properties>
        <property name="requiredSpacesAfterOpen" value="1" />
        <property name="requiredSpacesBeforeClose" value="1" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.Functions.FunctionDeclarationArgumentSpacing](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/Functions/FunctionDeclarationArgumentSpacingSniff.php)