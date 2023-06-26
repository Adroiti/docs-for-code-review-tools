Pattern: Use of empty statement

Issue: -

## Description

Typing mistakes and misunderstandings about where semicolons are required can lead to semicolons that are unnecessary. While not technically an error, extra semicolons can cause confusion when reading code.

## Default configuration

```xml
<module name="EmptyStatement"/>
```

## Examples

Example of **incorrect** code:

```java
doSomething();;

while (condition)
{
    ;
}
```

Example of **correct** code:

```java
doSomething();

while (condition)
{
    /** intentionally empty */
}
```


## Further Reading

* [checkstyle - EmptyStatement](https://checkstyle.sourceforge.io/checks/coding/emptystatement.html#EmptyStatement)
