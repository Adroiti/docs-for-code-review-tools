Pattern: Use of `Object.assign()`

Issue: -

## Description

Enforces the use of the ES2015 object spread operator over `Object.assign()` where appropriate.  
  
Rationale: Object spread allows for better type checking and inference.

## Further Reading

* [TSLint - prefer-object-spread](https://palantir.github.io/tslint/rules/prefer-object-spread)