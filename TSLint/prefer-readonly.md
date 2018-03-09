Pattern: Missing use of `readonly` for private variable

Issue: -

## Description

Requires that private variables are marked as `readonly` if they’re never modified outside of the constructor.  
  
Rationale: Marking never-modified variables as `readonly` helps enforce the code’s intent of keeping them as never-modified. It can also help prevent accidental changes of members not meant to be changed.

## Further Reading

* [TSLint - prefer-readonly](https://palantir.github.io/tslint/rules/prefer-readonly)