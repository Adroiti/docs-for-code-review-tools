Pattern: No namespace

Issue: -

## Description

Disallows use of internal `module`s and `namespace`s.  
  
Rationale: ES6-style external modules are the standard way to modularize code. Using `module {}` and `namespace {}` are outdated ways to organize TypeScript code.

## Further Reading

* [TSLint - no-namespace](https://palantir.github.io/tslint/rules/no-namespace)