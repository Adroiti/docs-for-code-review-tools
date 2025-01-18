Pattern: Non-null assertion with nullish coalescing

Issue: -

## Description

Using a non-null assertion (!) with the nullish coalescing operator (??) is contradictory since the nullish coalescing operator is specifically designed to handle null/undefined cases. The non-null assertion makes the nullish check redundant and indicates confusion about the operators' purposes.

## Examples

Example of **incorrect** code:
```ts
// Non-null assertion with nullish coalescing
const value = maybeValue! ?? defaultValue;

// Property access with assertion
const name = obj.name! ?? 'unknown';

// Method call with assertion
const result = getData()! ?? [];

// Chained property access
const nested = obj.prop!.value! ?? defaultValue;

// With variable
let x: string | undefined;
x = getValue();
x! ?? defaultValue;
```

Example of **correct** code:
```ts
// Simple nullish coalescing
const value = maybeValue ?? defaultValue;

// Property access
const name = obj.name ?? 'unknown';

// Method call
const result = getData() ?? [];

// Chained property access
const nested = obj.prop?.value ?? defaultValue;

// With variable
let x: string | undefined;
x = getValue();
x ?? defaultValue;

// Type guard when non-null is known
if (maybeValue !== null) {
  const value = maybeValue;
}
```