Pattern: Unused expression or function call

Issue: -

## Description

Disallows unused expressions - statements which are not assignments or function calls (and thus usually no-ops).
  
Rationale: Detects potential errors where an assignment or function call was intended.

## Further Reading

* [TSLint - no-unused-expression](https://palantir.github.io/tslint/rules/no-unused-expression)
