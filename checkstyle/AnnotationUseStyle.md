Pattern: Incorrect annotation style

Issue: -

## Description

This check controls the style with the usage of annotations. 

## Examples

To configure the check:


```java
 <module name="AnnotationUseStyle"/>
```
        

To configure the check to enforce an `expanded` style, with a trailing array comma set to `never` and always including the closing parenthesis. 


```xml
<module name="AnnotationUseStyle">
    <property name="elementStyle" value="expanded"/>
    <property name="trailingArrayComma" value="never"/>
    <property name="closingParens" value="always"/>
</module>
```

## Further Reading

* [checkstyle - AnnotationUseStyle](http://checkstyle.sourceforge.net/config_annotation.html#AnnotationUseStyle)
