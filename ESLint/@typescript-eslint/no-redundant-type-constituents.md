Pattern: Redundant type in union or intersection

Issue: -

## Description

Type unions and intersections may contain constituents that are made redundant by other members. For example, 'string' in a union with a string literal, or 'any' in a union with any other type. These redundant constituents add noise to the type declaration and may indicate misunderstanding of type relationships.

## Examples

Example of **incorrect** code:
```ts
// any/unknown in unions
type T1 = any | string;
type T2 = unknown | number;

// never in unions outside return position
type T3 = never | boolean;

// Primitive with its literal
type T4 = string | 'hello';
type T5 = number | 42;
type T6 = boolean | true;

// any/never in intersections
type T7 = string & any;
type T8 = number & never;

// unknown in intersections
type T9 = boolean & unknown;

// Primitive with literal in intersection
type T10 = string & 'hello';
type T11 = number & 42;

// Multiple redundant types
type T12 = string | 'hello' | 'world' | number;
```

Example of **correct** code:
```ts
// Single top types
type T1 = any;
type T2 = unknown;

// Clean unions without redundancy
type T3 = string | number;
type T4 = 'hello' | 'world';
type T5 = true | false;

// Proper type intersections
type T6 = string & { length: 5 };
type T7 = number & { toString(): string };

// Union of literals
type Status = 'pending' | 'success' | 'error';

// Meaningful intersection
type StringNumber = string & { toFixed(): string };

// Return position never
function fail(): never {
  throw new Error();
}

// Proper use of unknown
type SafeData = unknown & { validate(): boolean };
```