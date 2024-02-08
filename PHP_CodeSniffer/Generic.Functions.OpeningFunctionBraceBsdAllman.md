Pattern: Malformed opening function brace (BSD Allman)

Issue: -

## Description

This rule checks the position of the opening brace of a function and/or closure (anonymous function).

## Configuration

`checkFunctions` and `checkClosures` properties can be used to have the rule check one or both of these code blocks.

```xml
<!-- Don't check function braces, but check closure braces. -->
<rule ref="Generic.Functions.OpeningFunctionBraceBsdAllman">
    <properties>
        <property name="checkFunctions" value="false" />
        <property name="checkClosures" value="true" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Generic.Functions.OpeningFunctionBraceBsdAllman](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/Functions/OpeningFunctionBraceBsdAllmanSniff.php)