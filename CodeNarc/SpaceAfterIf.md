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

* [CodeNarc - SpaceAfterIf](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#SpaceAfterIf)