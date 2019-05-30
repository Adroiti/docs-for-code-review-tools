Pattern: Incomplete JQuery deferred instance

Issue: -

## Description

When a JQuery Deferred instance is created, then either `reject()` or
`resolve()` must be called on it within all code branches in the scope.

## Further Reading

* [TSLint - jquery-deferred-must-complete](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)