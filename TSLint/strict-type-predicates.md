Pattern: Strict type predicates

Issue: -

## Description

Warns for type predicates that are always true or always false. Works for `typeof` comparisons to constants (e.g. `typeof foo === “string”`), and equality comparison to `null`/`undefined`. (TypeScript won’t let you compare `1 === 2`, but it has an exception for `1 === undefined`.) Does not yet work for `instanceof`. Does _not_ warn for `if (x.y)` where `x.y` is always truthy. For that, see strict-boolean-expressions.

## Further Reading

* [TSLint - strict-type-predicates](https://palantir.github.io/tslint/rules/strict-type-predicates)