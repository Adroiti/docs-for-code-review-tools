Pattern: Duplicate variable

Issue: -

## Description

Disallows duplicate variable declarations in the same block scope.  
  
Rationale: A variable can be reassigned if necessary - there’s no good reason to have a duplicate variable declaration.

## Further Reading

* [TSLint - no-duplicate-variable](https://palantir.github.io/tslint/rules/no-duplicate-variable)