Pattern: Malformed space after `switch`

Issue: -

## Description

Checks that there is exactly one space (blank) after the `switch` keyword and before the opening parenthesis.

Examples of violations:

``` groovy
switch(x) {                                 // violation
    case 1: println 'one'
}
switch  (x) {                               // violation
    case 1: println 'one'
}
```

## Further Reading

* [CodeNarc - SpaceAfterSwitch](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#spaceafterswitch-rule)