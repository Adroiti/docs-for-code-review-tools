Pattern: Usage of unsafe built-in types

Issue: -

## Description

This rule has been split into several more focused rules. Unsafe built-in types like `{}`, `Function`, `Object`, and wrapper types can lead to type safety issues. Use the following replacement rules instead:
- `no-restricted-types` for banning specific type names
- `no-empty-object-type` for preventing empty object type usage
- `no-unsafe-function-type` for preventing `Function` type usage
- `no-wrapper-object-types` for preventing wrapper object types

## Examples

Example of **incorrect** code:
```ts
type EmptyObj = {};
type Func = Function;
type Num = Number;
type Obj = Object;

function process(callback: Function) {
  callback();
}

const value: {} = someValue;
```

Example of **correct** code:
```ts
type EmptyObj = Record<string, never>;
type Func = () => void;
type Num = number;
type Obj = object;

function process(callback: () => void) {
  callback();
}

const value: Record<string, unknown> = someValue;
```