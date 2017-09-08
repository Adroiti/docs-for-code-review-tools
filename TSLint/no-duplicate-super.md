Pattern: Multiple calls to `super()`

Issue: -

## Description

Warns if `super()` appears twice in a constructor.  
  
Rationale: The second call to `super()` will fail at runtime.

## Further Reading

* [TSLint - no-duplicate-super](https://palantir.github.io/tslint/rules/no-duplicate-super)