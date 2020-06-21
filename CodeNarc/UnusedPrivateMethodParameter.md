Pattern: Unused private method parameter

Issue: -

## Description

Checks for parameters to private methods that are not referenced within the method body. Note that the `private` modifier is not currently "respected" by Groovy code (i.e., Groovy can access `private` members within other classes).

## Further Reading

* [CodeNarc - UnusedPrivateMethodParameter](https://codenarc.github.io/CodeNarc/codenarc-rules-unused.html#unusedprivatemethodparameter-rule)