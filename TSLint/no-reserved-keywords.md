Pattern: Use of reserved keyword

Issue: -

## Description

Deprecated - This rule can be replaced with TSLint's `variable-name`. 

Do not use reserved keywords as names of local variables, fields,
functions, or other identifiers. Since version 2.0.9 this rule accepts a
parameter called `allow-quoted-properties`. If true, interface
properties in quotes will be ignored. This can be a useful way to avoid
verbose suppress-warning comments for generated d.ts files.  

This rule has some overlap with the [tslint variable-name
rule](https://palantir.github.io/tslint/rules/variable-name); however,
the rule here finds more keywords and more usages.

## Further Reading

* [TSLint - no-reserved-keywords](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)