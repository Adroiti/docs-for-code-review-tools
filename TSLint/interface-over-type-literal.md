Pattern: Use of type literal

Issue: -

## Description

Prefer an interface declaration over a type literal (`type T = { ... }`)  
  
Rationale: Interfaces are generally preferred over type literals because interfaces can be implemented, extended and merged.

## Further Reading

* [TSLint - interface-over-type-literal](https://palantir.github.io/tslint/rules/interface-over-type-literal)