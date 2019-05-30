Pattern: Unneeded Mocha Done

Issue: -

## Description

A function declares a Mocha Done parameter but only resolves it
synchronously in the main function. The Mocha Done parameter can be
safely removed from the parameter list.

## Further Reading

* [TSLint - mocha-unneeded-done](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)