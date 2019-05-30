Pattern: Use of `typeof x === 'undefined'`

Issue: -

## Description

Do not use the idiom `typeof x === 'undefined'`. You can safely use the
simpler `x === undefined` or perhaps `x == null` if you want to check
for either null or undefined.

## Further Reading

* [TSLint - no-typeof-undefined](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)