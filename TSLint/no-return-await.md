Pattern: Unnecessary `return await`

Issue: -

## Description

An async function always wraps the return value in a Promise. Using `return await` just adds extra time before the overreaching promise is resolved without changing the semantics.

## Further Reading

* [TSLint - no-return-await](https://palantir.github.io/tslint/rules/no-return-await)