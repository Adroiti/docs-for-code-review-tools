Pattern: Use of space after `!`

Issue: -

## Description

Checks that there are no whitespace characters directly after the not (`!`) operator.

## Examples

```java
def negatedValue = ! value //violation

if (! items.empty()) { println "not empty" } //violation
```

## Further Reading

* [CodeNarc - SpaceAfterNotOperator](https://codenarc.org/codenarc-rules-formatting.html#spaceafternotoperator-rule)