Pattern: Forbidden constructor

Issue: -

## Description

Disallows access to the constructors of `String`, `Number`, and `Boolean`. Disallows constructor use such as `new Number(foo)` but does not disallow `Number(foo)`.
  
Rationale: There is little reason to use `String`, `Number`, or `Boolean` as constructors. In almost all cases, the regular function-call version is more appropriate.

## Further Reading

* [TSLint - no-construct](https://palantir.github.io/tslint/rules/no-construct)
* [Stack Overflow - new Number() vs Number()](https://stackoverflow.com/questions/4719320/new-number-vs-number)