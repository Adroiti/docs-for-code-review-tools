Pattern: Unnecessary bind on function

Issue: -

## Description

Prevents unnecessary and/or misleading scope bindings on functions.  
  
Rationale: `function` expressions that are immediately bound to `this` are equivalent to `() =>` arrow lambdas. Additionally, there’s no use in binding a scope to an arrow lambda, as it already has one.

## Further Reading

* [TSLint - unnecessary-bind](https://palantir.github.io/tslint/rules/unnecessary-bind)