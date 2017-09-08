Pattern: Use of `any` as type declaration

Issue: -

## Description

Disallows usages of `any` as a type declaration.  
  
Rationale: Using `any` as a type declaration nullifies the compile-time benefits of the type system.

## Further Reading

* [TSLint - no-any](https://palantir.github.io/tslint/rules/no-any)