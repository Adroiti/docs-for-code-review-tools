Pattern: Use of implicit `it` closure parameter

Issue: -

## Description

Checks for the implicit `it` closure parameter being used. Also checks if an explicit `it` parameter has been specified.

Example of violations:

```groovy
    def closureWithViolation = { it * 10 }
    def closureWithViolationBecauseOfExplicitItParameter = { it -* it * 10}
```