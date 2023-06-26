Pattern: Use of empty block

Issue: -

## Description

Empty block statements, while not technically errors, usually occur due to refactoring that wasn’t completed. They can cause confusion when reading code.

By default, this rule disallows empty blocks for `if`, `else`, `switch`, `try` and `finally` statements. It ignores block statements which contain a comment (for example, in an finally block of try statement to indicate that execution should continue regardless of errors).

## Default configuration

```xml
<module name="EmptyBlock">
    <property name="option" value="TEXT"/>
    <property name="tokens" value="LITERAL_TRY, LITERAL_FINALLY, LITERAL_IF, LITERAL_ELSE, LITERAL_SWITCH"/>
</module>
```

## Examples

Example of **incorrect** code:

```java
if(optimistic)
{
}
else
{
}
```

Example of **correct** code:

```java
if(optimistic)
{
    message = "half full";
}
else
{
    message = "half empty";
}
```


## Further Reading

* [checkstyle - block policy](https://checkstyle.sourceforge.io/property_types/emptyblock.html#block)
* [checkstyle - EmptyBlock](http://checkstyle.sourceforge.net/config_blocks.html#EmptyBlock)
