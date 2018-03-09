Pattern: Use of dynamic `delete`

Issue: -

## Description

Bans usage of the delete operator with computed key expressions.  
  
Rationale: Deleting dynamically computed keys is dangerous and not well optimized.

## Further Reading

* [TSLint - no-dynamic-delete](https://palantir.github.io/tslint/rules/no-dynamic-delete)