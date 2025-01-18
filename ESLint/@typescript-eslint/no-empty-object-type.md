Pattern: Empty object type usage

Issue: -

## Description

The empty object type (`{}`) causes confusion because it represents any non-nullish value, not just objects. When developers use `{}`, they often intend to represent either any object (`object`) or any value including null/undefined (`unknown`). Using `{}` can hide type errors and lead to runtime issues.

## Examples

Example of **incorrect** code:
```ts
// Empty object type as variable type
let data: {};

// Empty interface definition
interface Config {}

// Type alias with empty object
type Options = {};

// Generic with empty object constraint
function process<T extends {}>() {}

// Function parameter with empty object
function handle(data: {}) {}

// Empty object in union
type Status = 'success' | {};
```

Example of **correct** code:
```ts
// Using 'object' for object values
let data: object;

// Using 'unknown' for any value
let value: unknown;

// Interface with properties
interface Config {
  debug: boolean;
}

// Type alias with properties
type Options = {
  timeout: number;
};

// Using specific type constraints
function process<T extends Record<string, unknown>>() {}

// Function with specific parameter type
function handle(data: Record<string, unknown>) {}

// Union with specific types
type Status = 'success' | Error;
```