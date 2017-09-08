Pattern: No unsafe finally

Issue: -

## Description

Disallows control flow statements, such as `return`, `continue`, `break` and `throws` in finally blocks.  
  
Rationale: When used inside `finally` blocks, control flow statements, such as `return`, `continue`, `break` and `throws` override any other control flow statements in the same try/catch scope. This is confusing and unexpected behavior.

## Further Reading

* [TSLint - no-unsafe-finally](https://palantir.github.io/tslint/rules/no-unsafe-finally)