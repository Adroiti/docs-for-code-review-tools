Pattern: Misplaced token location

Issue: -

## Description

By default this rule checks that:
- an open brace falls on the same line as its preceding expression.
- preceding whitespace for the specified tokens is present.

It can be also be configured to check that:

- `catch` is on the same line as the closing brace for `try`.
- `finally` is on the same line as the closing brace for `catch`.
- `else` is on the same line as the closing brace for `if`.


## Further Reading

* [TSLint - one-line](https://palantir.github.io/tslint/rules/one-line)
