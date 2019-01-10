Pattern: Missing use of `+= 1`/`-= 1`

Issue: -

## Description

Enforces using explicit `+= 1` or `-= 1` operators.  
  
Rationale: It’s easy to type +i or -i instead of –i or ++i, and won’t always result in invalid code. Prefer standardizing small arithmetic operations with the explicit += and -= operators.

## Further Reading

* [TSLint - increment-decrement](https://palantir.github.io/tslint/rules/increment-decrement)