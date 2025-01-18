Pattern: Primitive wrapper object type

Issue: -

## Description

Using uppercase wrapper object types (`Boolean`, `Number`, `String`, `BigInt`, `Symbol`, `Object`) instead of their lowercase primitive counterparts can lead to unexpected behavior in equality checks, truthiness evaluations, and arithmetic operations. Primitive types provide more predictable behavior and better type safety.

## Examples

Example of **incorrect** code:
```ts
let myBigInt: BigInt;
let myBoolean: Boolean;
let myNumber: Number;
let myString: String;
let mySymbol: Symbol;

let myObject: Object = 'string'; // Object allows primitives
```

Example of **correct** code:
```ts
let myBigint: bigint;
let myBoolean: boolean;
let myNumber: number;
let myString: string;
let mySymbol: symbol;

let myObject: object = {}; // object only allows object values
```