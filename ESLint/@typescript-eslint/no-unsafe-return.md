Pattern: Return of any type from function

Issue: -

## Description

Returning `any` typed values from functions creates type safety holes that can propagate through the codebase. This includes returning plain `any`, `any[]`, `Promise<any>` from async functions, and returning `any` in generic positions (like returning `Set<any>` when `Set<string>` is expected).

## Examples

Example of **incorrect** code:
```ts
function foo1() {
  return 1 as any;
}
function foo2() {
  return Object.create(null);
}
const foo3 = () => [] as any[];

const foo4 = (): string[] => [1, 2, 3] as any[];

async function foo5() {
  return Promise.resolve({} as any);
}

// Generic position examples
function assignability1(): Set<string> {
  return new Set<any>([1]);
}
type TAssign = () => Set<string>;
const assignability2: TAssign = () => new Set<any>([true]);
```

Example of **correct** code:
```ts
function foo1() {
  return 1;
}
function foo2() {
  return Object.create(null) as Record<string, unknown>;
}

const foo3 = () => [];
const foo4 = () => ['a'];

async function foo5() {
  return Promise.resolve(1);
}

function assignability1(): Set<string> {
  return new Set<string>(['foo']);
}
type TAssign = () => Set<string>;
const assignability2: TAssign = () => new Set(['foo']);
```