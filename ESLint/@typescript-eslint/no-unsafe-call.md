Pattern: Function call with any type

Issue: -

## Description

Calling a value typed as `any` disables TypeScript's type checking for that function call, creating potential runtime errors. This includes direct calls to `any` typed values, calling methods on `any` objects, using `any` values as constructors, and using `any` values as template literal tag functions.

## Examples

Example of **incorrect** code:
```ts
declare const anyVar: any;
declare const nestedAny: { prop: any };

anyVar();
anyVar.a.b();

nestedAny.prop();
nestedAny.prop['a']();

new anyVar();
new nestedAny.prop();

anyVar`foo`;
nestedAny.prop`foo`;

// Function type is also unsafe
const f: Function = () => {};
f();
```

Example of **correct** code:
```ts
declare const typedVar: () => void;
declare const typedNested: { prop: { a: () => void } };

typedVar();
typedNested.prop.a();

(() => {})();

new Map();

String.raw`foo`;
```