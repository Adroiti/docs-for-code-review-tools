Pattern: Union type with `null` and `undefined`

Issue: -

## Description

Disallows explicitly declared or implicitly returned union types with both `null` and `undefined` as members.  
  
Rationale: A union type that includes both `null` and `undefined` is either redundant or fragile. Enforcing the choice between the two allows the `triple-equals` rule to exist without exceptions, and is essentially a more flexible version of the `no-null-keyword` rule. Optional parameters are not considered to have the type `undefined`.

## Further Reading

* [TSLint - no-null-undefined-union](https://palantir.github.io/tslint/rules/no-null-undefined-union)