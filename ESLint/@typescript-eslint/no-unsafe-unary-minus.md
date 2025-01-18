Pattern: Unary minus on non-numeric type

Issue: -

## Description

Using the unary minus operator (-) on non-numeric types can produce unexpected results like NaN. The operator should only be used with number or bigint types to ensure predictable numeric operations.

## Examples

Example of **incorrect** code:
```ts
declare const a: string;
-a;

declare const b: {};
-b;
```

Example of **correct** code:
```ts
-42;
-42n;

declare const a: number;
-a;

declare const b: bigint;
-b;

declare const c: number | bigint;
-c;

declare const d: 1 | 2;
-d;
```