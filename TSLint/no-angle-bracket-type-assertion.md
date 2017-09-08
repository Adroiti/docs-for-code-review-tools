Pattern: Use of `<>` type assertion syntax

Issue: -

## Description

Requires the use of `as Type` for type assertions instead of `<Type>`.  
  
Rationale: Both formats of type assertions have the same effect, but only `as` type assertions work in `.tsx` files. This rule ensures that you have a consistent type assertion style across your codebase.

## Further Reading

* [TSLint - no-angle-bracket-type-assertion](https://palantir.github.io/tslint/rules/no-angle-bracket-type-assertion)