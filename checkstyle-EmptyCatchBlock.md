Pattern: Use of empty `catch` block

Issue: -

## Description

Except as noted below, it is very rarely correct to do nothing in response to a caught exception. Typical responses are to log it, or if it is considered "impossible", rethrow it as an `AssertionError`.

When it truly is appropriate to take no action whatsoever in a catch block, this rule enforces to have a comment to explain the reason this is justified.

**Exception**: In tests, a caught exception may be ignored without comment _if_ its name is or begins with expected. The following is a very common idiom for ensuring that the code under test _does_ throw an exception of the expected type, so a comment is unnecessary here.

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
} catch (NumberFormatException exception) {
}
return handleTextResponse(response);
```

Example of **correct** code:

```java
try {
  int i = Integer.parseInt(response);
  return handleNumericResponse(i);
} catch (NumberFormatException exception) {
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
