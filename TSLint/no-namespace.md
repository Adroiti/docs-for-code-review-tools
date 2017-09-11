Pattern: Use of 'namespace' or 'module'

Issue: -

## Description

Disallows use of internal modules and namespaces. This rule still allows the use of `declare module ... {}`.
  
Rationale: ES6-style external modules are the standard way to modularize code. Using `module {}` and `namespace {}` are outdated ways to organize TypeScript code.

## Further Reading

* [TSLint - no-namespace](https://palantir.github.io/tslint/rules/no-namespace)