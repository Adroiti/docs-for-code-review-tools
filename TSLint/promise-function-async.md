Pattern: Missing `async` for promise function

Issue: -

## Description

Requires any function or method that returns a promise to be marked `async`.  
  
Rationale: Ensures that each function is only capable of 

1) returning a rejected promise, or 
2) throwing an Error object. In contrast, non-`async` `Promise`-returning functions are technically capable of either. 

This practice removes a requirement for consuming code to handle both cases.

## Further Reading

* [TSLint - promise-function-async](https://palantir.github.io/tslint/rules/promise-function-async)