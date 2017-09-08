Pattern: Redundant type predicate

Issue: -

## Description

Warns for type predicates that are always true or always false. Works for `typeof` comparisons to constants (e.g. `typeof foo === “string”`), and equality comparison to `null`/`undefined`.

## Further Reading

* [TSLint - strict-type-predicates](https://palantir.github.io/tslint/rules/strict-type-predicates)