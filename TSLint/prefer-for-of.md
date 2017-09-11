Pattern: Use of `for` loop with simple iteration

Issue: -

## Description

Recommends a `for-of` loop over a standard `for` loop if the index is only used to access the array being iterated.  
  
Rationale: A for(… of …) loop is easier to implement and read when the index is not needed.

## Further Reading

* [TSLint - prefer-for-of](https://palantir.github.io/tslint/rules/prefer-for-of)
