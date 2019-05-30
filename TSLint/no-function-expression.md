Pattern: Use of function expression

Issue: -

## Description

Do not use function expressions; use arrow functions (lambdas) instead.
In general, lambdas are simpler to use and avoid the confusion about
what the `this` references points to. Function expressions that contain
a `this` reference are allowed and will not create a failure.

## Further Reading

* [TSLint - no-function-expression](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)