Pattern: Inconsistent use of `_` function

Issue: -

## Description

Enforce a consistent usage of `_` functions. By default, invoking
underscore functions should begin with wrapping a variable in an
underscore instance: `_(list).map(...)`. An alternative is to prefer
using the static methods on the `_` variable: `_.map(list, ...)`. 

## Configuration

The rule accepts a single parameter called `style` which can be the value 'static' or 'instance': `[true, { "style": "static" }]`.

## Further Reading

* [TSLint - underscore-consistent-invocation](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)