Pattern: Malformed space after `for`

Issue: -

## Description

Check that there is exactly one space (blank) after the `for` keyword and before the opening parenthesis.

Examples of violations:

``` groovy
for(name in names) { }                  // violation
for  (int i=0; i < 10; i++) { }         // violation
```

## Further Reading

* [CodeNarc - SpaceAfterFor](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#SpaceAfterFor)