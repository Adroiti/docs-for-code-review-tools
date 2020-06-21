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

* [CodeNarc - SpaceAfterCatch](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#spaceaftercatch-rule)