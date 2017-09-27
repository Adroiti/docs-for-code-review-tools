Pattern: Malformed space after `catch`

Issue: -

## Description

Checks that there is exactly one space (blank) after the `catch` keyword and before the opening parenthesis.

Examples of violations:

``` groovy
try { } catch(Exception e) { }          // violation
try { } catch  (Exception e) { }        // violation
```

## Further Reading

* [CodeNarc - SpaceAfterCatch](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#SpaceAfterCatch)