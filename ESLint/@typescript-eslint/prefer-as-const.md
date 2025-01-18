Pattern: Type assertion over as const

Issue: -

## Description

Using explicit type assertions for literal values is more verbose and requires duplicating the literal value in the type annotation. The `as const` assertion provides the same literal type inference with less code and reduces the risk of type mismatches.

## Examples

Example of **incorrect** code:
```ts
let bar: 2 = 2;
let foo = <'bar'>'bar';
let foo = { bar: 'baz' as 'baz' };
```

Example of **correct** code:
```ts
let foo = 'bar' as const;
let foo: 'bar' = 'bar' as const;
let bar = 'bar' as string;
let foo = <string>'bar';
let foo = { bar: 'baz' };
```