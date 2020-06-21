Pattern: Use of multiple `if` instead of `switch`

Issue: -

## Description

Checks for three of more `if` statements that could be converted to a `switch`. Only applies to equality and `instanceof`.

Example of violations:

``` groovy
if (x == 1) {                       // violation
   y = x
} else if (x == 2) {
   y = x * 2
} else if (x == 3) {
   y = x * 3
} else {
   y = 0
}

if (y instanceof Integer) {         // violation
   x = y + 1
}
if (y instanceof String) {
   x = y + '1'
} else if (y instanceof Boolean) {
   x = !y
} else {
   x = null
}

if (x == 1) {                       // OK
    y = x
}
if (x == 2) {
    y = x * 2
} else {
    y = 0
}

if (!x && y) {                      // OK
    doSomething()
} else if (!x && z) {
    doSomethingElse()
} else if (!x && i) {
    doAnotherThing()
}
```

## Further Reading

* [CodeNarc - CouldBeSwitchStatement](https://codenarc.github.io/CodeNarc/codenarc-rules-convention.html#couldbeswitchstatement-rule)