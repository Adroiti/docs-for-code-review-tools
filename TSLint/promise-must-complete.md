Pattern: Incomplete `Promise`

Issue: -

## Description

When a Promise instance is created, then either the `reject()` or
`resolve()` parameter must be called on it within all code branches in the
scope.
  
This rule has some overlap with the [tslint no-floating-promises
rule](https://palantir.github.io/tslint/rules/no-floating-promises), but
they are substantially different.

## Further Reading

* [TSLint - promise-must-complete](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)