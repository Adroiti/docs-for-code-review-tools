Pattern: No this assignment

Issue: -

## Description

Disallows unnecessary references to `this`.  
  
Rationale: Assigning a variable to `this` instead of properly using arrow lambdas may be a symptom of pre-ES6 practices or not manging scope well.

## Further Reading

* [TSLint - no-this-assignment](https://palantir.github.io/tslint/rules/no-this-assignment)