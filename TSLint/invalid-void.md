Pattern: Invalid use of `void`

Issue: -

## Description

Disallows usage of `void` type outside of generic or return types. If `void` is used as return type, it shouldn’t be a part of intersection/union type.

The `void` type means “nothing” or that a function does not return any value, in contra with implicit `undefined` type which means that a function returns a value `undefined`. So “nothing” cannot be mixed with any other types. If you need this - use `undefined` type instead.

## Further Reading

* [TSLint - invalid-void](https://palantir.github.io/tslint/rules/invalid-void)