Pattern: Non-shorthand arrow function

Issue: -

## Description

Suggests to convert `() => { return x; }` to `() => x`.

Arrow function body can be simplified by omitting the curly braces and the keyword `return`.

## Further Reading

* [TSLint - arrow-return-shorthand](https://palantir.github.io/tslint/rules/arrow-return-shorthand)