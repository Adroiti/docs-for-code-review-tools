Pattern: Malformed space around `->`

Issue: -

## Description

Checks that there is at least one space (blank) or whitespace around each closure arrow (-&gt;) symbol.

Known limitations:

-   Does not catch violations if the closure arrow (-&gt;) is on a separate line from the start of the closure.

Example of violations:

``` groovy
def closure1 = {->}                             // violation
def closure2 = { ->}                            // violation
def closure3 = {-> }                            // violation
def closure4 = { count-> println 123 }          // violation
def closure5 = { count, name ->println 123 }    // violation
```

## Further Reading

* [CodeNarc - SpaceAroundClosureArrow](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#spacearoundclosurearrow-rule)