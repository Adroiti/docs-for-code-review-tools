Pattern: Multiple imports from the same module

Issue: -

## Description

Disallows multiple import statements from the same module.  
  
Rationale: Using a single import statement per module will make the code clearer because you can see everything being imported from that module on one line.

## Further Reading

* [TSLint - no-duplicate-imports](https://palantir.github.io/tslint/rules/no-duplicate-imports)