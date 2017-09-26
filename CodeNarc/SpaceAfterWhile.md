Pattern: Malformed space after `while`

Issue: -

## Description

Check that there is exactly one space (blank) after the `while` keyword and before the opening parenthesis.

Examples of violations:

``` groovy
while(true) { }             // violation
while  (true) { }           // violation
```

## Further Reading

* [CodeNarc - SpaceAfterWhile](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#SpaceAfterWhile)