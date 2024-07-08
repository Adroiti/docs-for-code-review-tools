Pattern: Overridden method is CPS transformed

Issue: -

## Description

Overridden methods of the standard library (e.g. from `java.lang.Object`) are often called from there and therefore must not be CPS transformed in Jenkins.

## Examples

```groovy
class SomeClass {

    @Override // Violation
    String toString() {
        return ''
    }

    @NonCPS
    @Override // OK
    boolean equals(Object other) {
        return false
    }
}
```

## Further Reading

* [CodeNarc - ObjectOverrideOnlyNonCpsMethods](https://codenarc.org/codenarc-rules-jenkins.html#objectoverrideonlynoncpsmethods-rule)