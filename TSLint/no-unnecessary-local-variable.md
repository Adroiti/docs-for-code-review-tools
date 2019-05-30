Pattern: Unnecessary local variable

Issue: -

## Description

Do not declare a variable only to return it from the function on the
next line. It is always less code to simply return the expression that
initializes the variable.

## Further Reading

* [TSLint - no-unnecessary-local-variable](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)