Pattern: Malformed space after `if`

Issue: -

## Description

Checks that there is exactly one space (blank) after the `if` keyword and before the opening parenthesis.

Examples of violations:

``` groovy
if(true) { }                            // violation
if  (true) { }                          // violation
```

## Further Reading

* [CodeNarc - SpaceAfterIf](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#spaceafterif-rule)