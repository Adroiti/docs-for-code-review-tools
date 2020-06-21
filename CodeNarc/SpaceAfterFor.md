Pattern: Malformed space after `for`

Issue: -

## Description

Checks that there is exactly one space (blank) after the `for` keyword and before the opening parenthesis.

Examples of violations:

``` groovy
for(name in names) { }                  // violation
for  (int i=0; i < 10; i++) { }         // violation
```

## Further Reading

* [CodeNarc - SpaceAfterFor](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#spaceafterfor-rule)