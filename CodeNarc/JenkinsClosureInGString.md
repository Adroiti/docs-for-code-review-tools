Pattern: GString contains a closure

Issue: -

## Description

Closures are CPS transformed by Jenkins and will cause an error at runtime when used in GStrings. Typically they can be replaced by variable interpolation. Closures that are used as argument to method calls on the other hand are fine.

## Examples

```groovy
def s1 = "some string ${-> x}" // Violation
def s2 = "some string ${x}" // OK
def s3 = "some string ${ [1,2,3].collect { i -> i * i }.toString() }" // OK
```

## Further Reading

* [CodeNarc - ClosureInGString](https://codenarc.org/codenarc-rules-jenkins.html#closureingstring-rule)