Pattern: Missing use of array literal

Issue: -

## Description

Use array literal syntax when declaring or instantiating array types.

For example, prefer the Javascript form of `string[]` to the TypeScript
form `Array<string>`. Prefer `[]` over `new Array()`. Prefer `[4, 5]`
over `new Array(4, 5)`. Prefer `[undefined, undefined]` over `new Array(2)`.  

## Configuration

Since `2.0.10`, this rule can be configured to allow `Array` type
parameters. To ignore type parameters, configure the rule with the
values: `[true, {"allow-type-parameters": true}]`.  
Since 6.2.0-beta, you can lift restriction on `Array` constructor calls
with a single argument (to create empty array of a given length). If
type information is available - rule will allow only a single argument
of `number` type. To allow empty array creation, configure the rule with
the values: `[true, {"allow-size-argument": true}]`.  
This rule has some overlap with the [TSLint array-type
rule](https://palantir.github.io/tslint/rules/array-type); however, the
version here catches more instances.

## Further Reading

* [TSLint - prefer-array-literal](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)