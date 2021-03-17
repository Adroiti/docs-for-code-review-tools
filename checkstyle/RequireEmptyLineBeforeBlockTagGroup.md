Pattern: Missing empty line before block tag

Issue: -

## Description

Checks that one blank line before the block tag if it is present in Javadoc. 

## Examples

By default, the check will report a violation if there is no blank line before the block tag, like in the example below. 

```java
/**
 * testMethod's javadoc.
 * @return something (violation)
 */
public boolean testMethod() {
    return false;
}
    
```

## Further Reading

* [checkstyle - RequireEmptyLineBeforeBlockTagGroup](http://checkstyle.sourceforge.net/config_javadoc.html#RequireEmptyLineBeforeBlockTagGroup)