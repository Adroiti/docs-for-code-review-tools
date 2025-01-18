Pattern: Function argument with any type

Issue: -

## Description

Passing `any` typed values as function arguments bypasses TypeScript's type checking and creates potential type safety issues. This includes spreading arrays or tuples with `any` typed elements, and passing `any` types in generic positions (like `Set<any>` to a parameter expecting `Set<string>`).

## Examples

Example of **incorrect** code:
```ts
declare function foo(arg1: string, arg2: number, arg3: string): void;

const anyTyped = 1 as any;
foo(...anyTyped);
foo(anyTyped, 1, 'a');

const anyArray: any[] = [];
foo(...anyArray);

const tuple1 = ['a', anyTyped, 'b'] as const;
foo(...tuple1);

const tuple2 = [1] as const;
foo('a', ...tuple2, anyTyped);

declare function bar(arg1: string, arg2: number, ...rest: string[]): void;
const x = [1, 2] as [number, ...number[]];
foo('a', ...x, anyTyped);

declare function baz(arg1: Set<string>, arg2: Map<string, string>): void;
foo(new Set<any>(), new Map<any, string>());
```

Example of **correct** code:
```ts
declare function foo(arg1: string, arg2: number, arg3: string): void;

foo('a', 1, 'b');

const tuple1 = ['a', 1, 'b'] as const;
foo(...tuple1);

declare function bar(arg1: string, arg2: number, ...rest: string[]): void;
const array: string[] = ['a'];
bar('a', 1, ...array);

declare function baz(arg1: Set<string>, arg2: Map<string, string>): void;
foo(new Set<string>(), new Map<string, string>());
```