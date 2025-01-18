Pattern: Empty interface declaration

Issue: -

## Description

⚠️ This rule is deprecated. Use `@typescript-eslint/no-empty-object-type` instead.

An empty interface adds no value as any non-null value can be assigned to it. Empty interfaces or those that only extend a single interface are often a sign of confusion about interface purpose or incomplete implementation. Such interfaces should either be populated with members or removed.

## Examples

Example of **incorrect** code:
```ts
// Empty interface
interface User {}

// Interface extending single interface without adding members
interface Employee extends Person {}

// Multiple empty interfaces
interface Request {}
interface Response {}

// Generic empty interface
interface Container<T> {}
```

Example of **correct** code:
```ts
// Interface with members
interface User {
  name: string;
  age: number;
}

// Interface extending multiple interfaces
interface Employee extends Person, Worker {}

// Interface with single member
interface Request {
  url: string;
}

// Generic interface with constraints
interface Container<T> {
  value: T;
  isEmpty: boolean;
}
```