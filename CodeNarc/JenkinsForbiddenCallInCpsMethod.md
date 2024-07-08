Pattern: Forbidden call in CPS method

Issue: -

## Description

Some methods from the standard library cannot be CPS transformed and therefore must not be called with CPS transformed closure arguments.

## Examples

```groovy
void cpsMethod() {
    List l = [4,1,3]
    l.sort { a, b -> a > b } // Violation
    l.toSorted { a, b -> a > b } // Violation
    "hello".eachLine { l, n -> println(l) } // Violation
    "hello".eachLine(2) { l, n -> println(l) } // Violation
}
```

## Further Reading

* [CodeNarc - ForbiddenCallInCpsMethod](https://codenarc.org/codenarc-rules-jenkins.html#forbiddencallincpsmethod-rule)