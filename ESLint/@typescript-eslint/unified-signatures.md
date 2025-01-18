Pattern: Redundant function overload

Issue: -

## Description

Having multiple function overload signatures when they could be combined using union types, optional parameters, or rest parameters adds unnecessary complexity. Unified signatures are easier to read and maintain while providing the same functionality.

## Examples

Example of **incorrect** code:
```ts
// Could use union type
function process(x: number): void;
function process(x: string): void;

// Could use optional parameter
function log(): void;
function log(message: string): void;

// Could use rest parameter
function sum(): void;
function sum(...numbers: number[]): void;

// Could use union type for parameters
function update(id: string, value: string): void;
function update(id: number, value: string): void;
```

Example of **correct** code:
```ts
// Using union type
function process(x: number | string): void;

// Using optional parameter
function log(message?: string): void;

// Using rest parameter
function sum(...numbers: number[]): void;

// Using union type for parameters
function update(id: string | number, value: string): void;

// Different rest parameter types are allowed 
// since they can't be unified
function combine(...args: string[]): void;
function combine(...args: number[]): void;
```