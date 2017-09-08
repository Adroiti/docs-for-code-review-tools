Pattern: No unsafe any

Issue: -

## Description

Warns when using an expression of type `any` in a dynamic way. Uses are only allowed if they would work for `{} | null | undefined`. Type casts and tests are allowed. Expressions that work on all values (such as `"" + x`) are allowed.

## Further Reading

* [TSLint - no-unsafe-any](https://palantir.github.io/tslint/rules/no-unsafe-any)