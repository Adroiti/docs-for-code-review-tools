Pattern: Invalid comparison in `typeof`

Issue: -

## Description

Deprecated - This rule is now enforced by the TypeScript compiler.

Ensures that the results of `typeof` are compared against a valid string.
This rule aims to prevent errors from likely typos by ensuring that when
the result of a `typeof` operation is compared against a string, that the
string is a valid value. 

Similar to the [valid-typeof](https://eslint.org/docs/rules/valid-typeof) ESLint rule.

## Further Reading

* [TSLint - valid-typeof](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)