Pattern: Explicit any type usage

Issue: -

## Description

The `any` type disables TypeScript's type checking and should be avoided. Using `any` undermines the purpose of TypeScript's type system and can hide real type errors. Instead, use specific types or `unknown` when the type cannot be known in advance.

## Examples

Example of **incorrect** code:
```ts
// any as variable type
let value: any;

// any in arrays
const items: any[] = [];
const list: Array<any> = [];

// any in function parameters
function process(data: any) {}

// any in function return
function getData(): any {}

// any in generic types
type Container<T = any> = { data: T };

// any in type assertions
const result = data as any;

// Nested any in arrays
const matrix: any[][] = [];
```

Example of **correct** code:
```ts
// Specific types
let value: string;
let mixed: string | number;

// Typed arrays
const items: string[] = [];
const list: Array<number> = [];

// Unknown for uncertain types
function process(data: unknown) {}

// Union types for multiple possibilities
type Status = 'pending' | 'success' | 'error';

// Proper generic constraints
type Container<T extends object> = { data: T };

// Type assertions to known types
const result = data as string;

// Type-safe array definitions
const matrix: number[][] = [];

// Rest parameters with specific types
function log(...messages: string[]) {}
```