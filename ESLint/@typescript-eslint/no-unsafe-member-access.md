Pattern: Member access on any type

Issue: -

## Description

Accessing members on values typed as `any` bypasses TypeScript's type checking and creates potential type safety holes. This includes dot notation access, bracket notation access, and using `any` typed values as indices for accessing array members.

## Examples

Example of **incorrect** code:
```ts
declare const anyVar: any;
declare const nestedAny: { prop: any };

anyVar.a;
anyVar.a.b;
anyVar['a'];
anyVar['a']['b'];

nestedAny.prop.a;
nestedAny.prop['a'];

const key = 'a';
nestedAny.prop[key];

// Using an any to access a member is unsafe
const arr = [1, 2, 3];
arr[anyVar];
nestedAny[anyVar];
```

Example of **correct** code:
```ts
declare const properlyTyped: { prop: { a: string } };

properlyTyped.prop.a;
properlyTyped.prop['a'];

const key = 'a';
properlyTyped.prop[key];

const arr = [1, 2, 3];
arr[1];
let idx = 1;
arr[idx];
arr[idx++];
```