Pattern: Use of string-based `setTimeout`

Issue: -

## Description

Do not use the version of `setTimeout` that accepts code as a string
argument. However, it is acceptable to use the version of `setTimeout`
where a direct reference to a function is provided as the callback
argument.

## Further Reading

* [TSLint - no-string-based-set-timeout](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)