Pattern: Unnecessary constructor

Issue: -

## Description

Prevents blank constructors, as they are redundant.  
  
Rationale: JavaScript implicitly adds a blank constructor when there isn’t one. It’s not necessary to manually add one in.

## Further Reading

* [TSLint - unnecessary-constructor](https://palantir.github.io/tslint/rules/unnecessary-constructor)