Pattern: Missing use of Chai `.contain()`

Issue: -

## Description

Avoid Chai assertions that invoke `indexOf` and compare for a -1 result.
It is better to use the chai `.contain()` assertion API instead because
the failure message will be clearer if the test fails.

## Further Reading

* [TSLint - chai-prefer-contains-to-index-of](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)