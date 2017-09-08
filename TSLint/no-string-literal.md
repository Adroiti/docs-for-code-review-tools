Pattern: No string literal

Issue: -

## Description

Forbids unnecessary string literal property access. Allows `obj["prop-erty"]` (can’t be a regular property access). Disallows `obj["property"]` (should be `obj.property`).  
  
Rationale: If `\--noImplicitAny` is turned off, property access via a string literal will be `any` if the property does not exist.

## Further Reading

* [TSLint - no-string-literal](https://palantir.github.io/tslint/rules/no-string-literal)