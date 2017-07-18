Pattern: Use of empty block

Issue: -

## Description

Checks for empty blocks. This check does not validate sequential blocks. 

Sequential blocks won't be checked. Also, no violations for fall through:

```java
switch (a) {
    case 1:                          // no violation
    case 2:                          // no violation
    case 3: someMethod(); { }        // no violation
    default: break;
}
```


This check processes LITERAL_CASE and LITERAL_DEFAULT separately. So, if tokens=LITERAL_DEFAULT, following code will not trigger any violation, as the empty block belongs to LITERAL_CASE: 

Configuration:

```xml
<module name="EmptyBlock">
    <property name="tokens" value="LITERAL_DEFAULT"/>
</module>
```


Result:
```java
switch (a) {
    default:        // no violation for "default:" as empty block belong to "case 1:"
    case 1: { }
}
```


## Examples

To configure the check: 

```xml
<module name="EmptyBlock"/>
```

To configure the check for the `text` policy and only `try` blocks:

```xml
<module name="EmptyBlock">
    <property name="option" value="text"/>
    <property name="tokens" value="LITERAL_TRY"/>
</module>
```


## Further Reading

* [checkstyle - EmptyBlock](http://checkstyle.sourceforge.net/config_blocks.html#EmptyBlock)
