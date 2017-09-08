Pattern: No floating promises

Issue: -

## Description

Promises returned by functions must be handled appropriately.  
  
Rationale: Unhandled Promises can cause unexpected behavior, such as resolving at unexpected times.

## Further Reading

* [TSLint - no-floating-promises](https://palantir.github.io/tslint/rules/no-floating-promises)