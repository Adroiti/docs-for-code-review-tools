Pattern: Type assertion that doesn't change type

Issue: -

## Description

Type assertions using `as` or angle brackets that don't change the type of an expression increase visual clutter and reduce code readability. If the assertion results in the same type as TypeScript would infer automatically, it should be removed.

## Examples

Example of **incorrect** code:
```ts
const foo = 3;
const bar = foo!;

const foo = <number>(3 + 5);

type Foo = number;
const foo = <Foo>(3 + 5);
const foo = (3 + 5) as Foo;

const foo = 'foo' as const;

function foo(x: number): number {
  return x!; // unnecessary non-null
}
```

Example of **correct** code:
```ts
const foo = <number>3;
const foo = 3 as number;

let foo = 'foo' as const;

function foo(x: number | undefined): number {
  return x!;
}
```