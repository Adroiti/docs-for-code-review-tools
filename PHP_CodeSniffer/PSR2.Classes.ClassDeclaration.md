Pattern: Malformed class declaration

Issue: -

## Description

Checks the declaration of the class and its inheritance is correct.

## Configuration

By default, this rule ensures that the class names are indented 4 spaces, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="PSR2.Classes.ClassDeclaration">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - PSR2.Classes.ClassDeclaration](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/PSR2/Sniffs/Classes/ClassDeclarationSniff.php)