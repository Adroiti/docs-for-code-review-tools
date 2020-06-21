Pattern: Unnecessary string instantiation

Issue: -

## Description

Checks for direct call to the `String` constructor that accepts a `String` literal. In almost all cases, this is unnecessary. Use a `String` literal (e.g., `"..."`) instead of calling the corresponding `String` constructor (`new String("..")`) directly.

Here is an example of code that produces a violation:

``` groovy
def s = new String('abc')
```

## Further Reading

* [CodeNarc - UnnecessaryStringInstantiation](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessarystringinstantiation-rule)