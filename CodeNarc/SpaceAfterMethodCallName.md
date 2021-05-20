Pattern: Use of space after method name

Issue: -

## Description

Checks that there is no whitespace after the method name when a method call contains parenthesis or that there is at most one space after the method name if the call does not contain parenthesis.

## Examples

```java
aMethod ("arg") //violation

aMethod  "arg" //violation

throw new Exception () //violation
```

## Further Reading

* [CodeNarc - SpaceAfterMethodCallName](https://codenarc.org/codenarc-rules-formatting.html#spaceaftermethodcallname-rule)