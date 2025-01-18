Pattern: Redundant type annotation on initializer

Issue: -

## Description

TypeScript can infer types for variables, parameters, and properties from their initial or default values. Adding explicit type annotations in these cases adds unnecessary verbosity and can prevent TypeScript from inferring more specific literal types.

## Examples

Example of **incorrect** code:
```ts
// Primitives with obvious types
const count: number = 5;
const name: string = "John";
const enabled: boolean = true;

// Built-in types with clear initialization
const regex: RegExp = /test/;
const now: Date = new Date();
const sym: symbol = Symbol('desc');

// Class properties with initializers
class User {
  name: string = 'guest';
  age: number = 0;
  active: boolean = false;
}

// Function parameters with defaults
function greet(name: string = 'world'): void {}
function increment(value: number = 0): number {
  return value + 1;
}
```

Example of **correct** code:
```ts
// Let TypeScript infer the types
const count = 5;
const name = "John";
const enabled = true;

// Built-in type inference
const regex = /test/;
const now = new Date();
const sym = Symbol('desc');

// Class with inferred property types
class User {
  name = 'guest';
  age = 0;
  active = false;

  // Type annotation needed when no initializer
  role: string;
}

// Function with inferred parameter types
function greet(name = 'world') {}
function increment(value = 0) {
  return value + 1;
}

// Type annotations needed for null/undefined
let status: string | null = null;
let data: number | undefined;
```