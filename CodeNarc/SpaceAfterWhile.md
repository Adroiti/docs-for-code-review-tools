Pattern: Malformed space after `while`

Issue: -

## Description

Checks that there is exactly one space (blank) after the `while` keyword and before the opening parenthesis.

Examples of violations:

``` groovy
while(true) { }             // violation
while  (true) { }           // violation
```

## Further Reading

* [CodeNarc - SpaceAfterWhile](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#spaceafterwhile-rule)