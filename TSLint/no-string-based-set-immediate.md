Pattern: Use of string-based `setImmediate`

Issue: -

## Description

Do not use the version of `setImmediate` that accepts code as a string
argument. However, it is acceptable to use the version of `setImmediate`
where a direct reference to a function is provided as the callback
argument.

## Further Reading

* [TSLint - no-string-based-set-immediate](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)