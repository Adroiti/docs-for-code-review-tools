Pattern: Variable use before declaration

Issue: -

## Description

Disallows usage of variables before their declaration.

This rule is primarily useful when using the `var` keyword - the compiler will detect if a `let` and `const` variable is used before it is declared.

## Further Reading

* [TSLint - no-use-before-declare](https://palantir.github.io/tslint/rules/no-use-before-declare)