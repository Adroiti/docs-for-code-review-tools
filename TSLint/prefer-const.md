Pattern: Missing `const` for variable declaration

Issue: -

## Description

Requires that variable declarations use `const` instead of `let` and `var` if possible.

If a variable is only assigned to once when it is declared, it should be declared using `const`.

## Further Reading

* [TSLint - prefer-const](https://palantir.github.io/tslint/rules/prefer-const)