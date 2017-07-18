Pattern: Line is too long

Issue: -

## Description

Your source code should not contain very long lines. The default wrapping in most tools disrupts the visual structure of the code, making it more difficult to understand.

## Examples

To configure the check to accept lines up to 120 characters long: 


```xml
<module name="LineLength">
    <property name="max" value="120"/>
</module>
```

To configure the check to ignore lines that begin with ` * `, followed by just one word, such as within a Javadoc comment: 


```xml
<module name="LineLength">
   <property name="ignorePattern" value="^ *\* *[^ ]+$"/>
</module>
```

## Further Reading

* [checkstyle - LineLength](http://checkstyle.sourceforge.net/config_sizes.html#LineLength)
