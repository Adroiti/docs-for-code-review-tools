Pattern: Use of empty `catch` block

Issue: -

## Description

Except as noted below, it is very rarely correct to do nothing in response to a caught exception. Typical responses are to log it, or if it is considered "impossible", rethrow it as an `AssertionError`.

## Default configuration

```xml
<module name="EmptyCatchBlock">
    <property name="exceptionVariableName" value="expected"/>
</module>
```

## Examples

Example of **incorrect** code:

```java
try {
  int i = Integer.parseInt(response);
  return handleNumericResponse(i);
} catch (NumberFormatException ok) {
}
return handleTextResponse(response);
```

Example of **correct** code:

```java
try {
  int i = Integer.parseInt(response);
  return handleNumericResponse(i);
} catch (NumberFormatException ok) {
  // it's not numeric; that's fine, just continue
}
return handleTextResponse(response);
```        


To configure the check to suppress empty `catch` block if single-line comment inside is `//This is expected` or exception's variable name is `myException` (any option is matching): 


```xml
<module name="EmptyCatchBlock">
    <property name="commentFormat" value="This is expected"/>
    <property name="exceptionVariableName" value="myException"/>
</module>
```

## Further Reading

* [Google Java Style Guide - Caught exceptions: not ignored](https://google.github.io/styleguide/javaguide.html#s6.2-caught-exceptions)
* [checkstyle - EmptyCatchBlock](http://checkstyle.sourceforge.net/config_blocks.html#EmptyCatchBlock)
