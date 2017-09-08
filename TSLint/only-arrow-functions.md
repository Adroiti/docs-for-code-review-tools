Pattern: Use of non-arrow function

Issue: -

## Description

Disallows traditional (non-arrow) function expressions.  
  
Rationale: Traditional functions don’t bind lexical scope, which can lead to unexpected behavior when accessing `this`.

## Further Reading

* [TSLint - only-arrow-functions](https://palantir.github.io/tslint/rules/only-arrow-functions)