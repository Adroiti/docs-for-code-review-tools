Pattern: Assignment of any type

Issue: -

## Description

The `any` type can leak into codebases through variable assignments, array destructuring, and generic type arguments. This creates type safety holes as `any` bypasses TypeScript's type checking. This includes assigning `any[]` to array destructuring patterns and passing `any` types in generic positions (like `Set<any>` to `Set<string>`).

## Examples

Example of **incorrect** code:
```ts
const x = 1 as any, y = 1 as any;
const [x] = 1 as any;
const [x] = [] as any[];
const [x] = [1 as any];
[x] = [1] as [any];

function foo(a = 1 as any) {}
class Foo {
  constructor(private a = 1 as any) {}
}
class Foo {
  private a = 1 as any;
}

// Generic position examples
const x: Set<string> = new Set<any>();
const x: Map<string, string> = new Map<string, any>();
const x: Set<string[]> = new Set<any[]>();
const x: Set<Set<Set<string>>> = new Set<Set<Set<any>>>();
```

Example of **correct** code:
```ts
const x = 1, y = 1;
const [x] = [1];
[x] = [1] as [number];

function foo(a = 1) {}
class Foo {
  constructor(private a = 1) {}
}
class Foo {
  private a = 1;
}

// Generic position examples
const x: Set<string> = new Set<string>();
const x: Map<string, string> = new Map<string, string>();
const x: Set<string[]> = new Set<string[]>();
const x: Set<Set<Set<string>>> = new Set<Set<Set<string>>>();
```