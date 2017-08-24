Pattern: Unresolved warning comment

Issue: -

## Description

Developers often add comments to code which is not complete or needs review. Most likely you want to fix or review the code, and then remove the comment, before you consider the code to be production ready.

## Default configuration

```xml
<module name="TodoComment">
    <property name="format" value="(TODO)|(FIXME)"/>
    <message key="todo.match" value="Resolve unexpected comment."/>
</module>
```

## Examples

Example of **incorrect** code:

```java
// FIXME: this is not a good idea
// TODO: need code review
doSomethingExperimental();
```

Example of **correct** code:

```java
// NOT READY FOR PRIME TIME
// but too bad, it is not a predefined warning term
doSomethingExperimental();
```


## Further Reading

* [checkstyle - TodoComment](http://checkstyle.sourceforge.net/config_misc.html#TodoComment)
