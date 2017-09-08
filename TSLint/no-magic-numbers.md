Pattern: No magic numbers

Issue: -

## Description

Disallows the use constant number values outside of variable assignments. When no list of allowed values is specified, -1, 0 and 1 are allowed by default.  
  
Rationale: Magic numbers should be avoided as they often lack documentation, forcing them to be stored in variables gives them implicit documentation.

## Further Reading

* [TSLint - no-magic-numbers](https://palantir.github.io/tslint/rules/no-magic-numbers)