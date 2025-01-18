Pattern: Inconsistent spacing around commas

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent spacing before and after commas, which can now be configured using the stylistic plugin's comma-spacing rule.

## Examples

Example of **incorrect** code:
```ts
const arr = [1,2 ,3 , 4];
function foo(a,b,c) {}
type Props = {
  name:string,age:number
};
const obj = {
  foo:1,bar :2 ,baz:3
};
```

Example of **correct** code:
```ts
const arr = [1, 2, 3, 4];
function foo(a, b, c) {}
type Props = {
  name: string, age: number
};
const obj = {
  foo: 1, bar: 2, baz: 3
};
```

See [eslint.style](https://eslint.style) for the current version of this rule.