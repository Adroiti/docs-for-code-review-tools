Pattern: Unnecessary `.class`

Issue: -

## Description

To make a reference to a class, it is unnecessary to specify the `.class` identifier. For instance `String.class` can be shortened to `String`.

Example of violations:

``` groovy
// The '.class' identifier is unnecessary, violation occurs
def x = String.class

// Ok, unnecessary '.class' identifier has been excluded
def x = String
```

## Further Reading

* [CodeNarc - UnnecessaryDotClass](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessarydotclass-rule)