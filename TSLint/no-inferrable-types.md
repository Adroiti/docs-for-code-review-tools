Pattern: Explicit number, string, or boolean declaration

Issue: -

## Description

Disallows explicit type declarations for variables or parameters initialized to a number, string, or boolean.  
  
Rationale: Explicit types where they can be easily inferred by the compiler make code more verbose.

## Further Reading

* [TSLint - no-inferrable-types](https://palantir.github.io/tslint/rules/no-inferrable-types)