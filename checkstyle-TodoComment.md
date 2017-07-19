Pattern: Unresolved warning comment

Issue: -

## Description

Developers often add comments to code which is not complete or needs review. Most likely you want to fix or review the code, and then remove the comment, before you consider the code to be production ready.

```java
// FIXME: this is not a good idea
// TODO: do something
```

## Examples

To configure the check: 


```xml
<module name="TodoComment"/>
```
        

To configure the check for comments that contain `TODO` and `FIXME`: 


```xml
<module name="TodoComment">
    <property name="format" value="(TODO)|(FIXME)"/>
</module>
```

## Further Reading

* [checkstyle - TodoComment](http://checkstyle.sourceforge.net/config_misc.html#TodoComment)
