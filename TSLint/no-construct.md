Pattern: No construct

Issue: -

## Description

Disallows access to the constructors of `String`, `Number`, and `Boolean`.  
  
Rationale: There is little reason to use `String`, `Number`, or `Boolean` as constructors. In almost all cases, the regular function-call version is more appropriate. [More details](http://stackoverflow.com/q/4719320/3124288) are available on StackOverflow.

## Further Reading

* [TSLint - no-construct](https://palantir.github.io/tslint/rules/no-construct)