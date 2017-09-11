Pattern: Duplicate variable

Issue: -

## Description

Disallows duplicate variable declarations in the same block scope. This rule is only useful when using the `var` keyword - the compiler will detect redeclarations of `let` and `const` variables.
  
Rationale: A variable can be reassigned if necessary - there’s no good reason to have a duplicate variable declaration.

## Further Reading

* [TSLint - no-duplicate-variable](https://palantir.github.io/tslint/rules/no-duplicate-variable)