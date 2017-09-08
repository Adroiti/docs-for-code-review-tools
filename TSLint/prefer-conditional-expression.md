Pattern: Same assignment in multiple places

Issue: -

## Description

Recommends to use a conditional expression instead of assigning to the same thing in each branch of an if statement.  
  
Rationale: This reduces duplication and can eliminate an unnecessary variable declaration.

## Further Reading

* [TSLint - prefer-conditional-expression](https://palantir.github.io/tslint/rules/prefer-conditional-expression)