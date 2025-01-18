Pattern: Type assertion that narrows type

Issue: -

## Description

Type assertions that narrow a type bypass TypeScript's type checking and can lead to runtime errors. While type assertions that broaden types are safe because they make TypeScript know less about a type, narrowing assertions can hide potential type mismatches that TypeScript would otherwise catch.

## Examples

Example of **incorrect** code:
```ts
function f() {
  return Math.random() < 0.5 ? 42 : 'oops';
}

const z = f() as number;

const items = [1, '2', 3, '4'];
const number = items[0] as number;
```

Example of **correct** code:
```ts
function f() {
  return Math.random() < 0.5 ? 42 : 'oops';
}

const z = f() as number | string | boolean;

const items = [1, '2', 3, '4'];
const number = items[0] as number | string | undefined;
```