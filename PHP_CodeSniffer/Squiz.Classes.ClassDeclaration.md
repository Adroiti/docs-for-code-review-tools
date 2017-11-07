Pattern: Incorrect class declaration

Issue: -

## Description

Checks the declaration of the class and its inheritance is correct.

## Configuration

By default, this rule ensures that the class names are indented 4 spaces, but you can change the size of the indent by setting the `indent` property.

```xml
<rule ref="Squiz.Classes.ClassDeclaration">
    <properties>
        <property name="indent" value="2" />
    </properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - Squiz.Classes.ClassDeclaration](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/Classes/ClassDeclarationSniff.php)