Pattern: Addition with incompatible types

Issue: -

## Description

Using the `+` operator with operands of different types or with types other than `bigint`, `number`, or `string` can lead to unexpected coercions and results. This is particularly problematic when combining values produces `[object Object]` or incorrect type conversions.

## Examples

Example of **incorrect** code:
```ts
// Mixing different numeric types
let foo = 1n + 1;

// Mixing incompatible types
let x = {} + 'string';
let y = [] + 23;
const z = Symbol() + 'abc';

// Function parameters with incompatible types
let fn = (a: string, b: never) => a + b;
let add = (x: number, y: {}) => x + y;
```

Example of **correct** code:
```ts
// Same type numeric operations
let foo = 1n + 1n;
let bar = 1 + 1;

// String concatenation
let str = 'hello' + 'world';

// Function parameters with compatible types
let fn = (a: string, b: string) => a + b;
let add = (x: number, y: number) => x + y;

// Explicit toString conversion
const obj = {};
let str = 'Value: ' + obj.toString();
```