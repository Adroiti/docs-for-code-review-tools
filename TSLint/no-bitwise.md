Pattern: Use of bitwise operation

Issue: -

## Description

Disallows bitwise operators.  
  
Rationale: Bitwise operators are often typos - for example `bool1 & bool2` instead of `bool1 && bool2`. They also can be an indicator of overly clever code which decreases maintainability.

## Further Reading

* [TSLint - no-bitwise](https://palantir.github.io/tslint/rules/no-bitwise)