Pattern: Missing type annotation at module boundary

Issue: -

## Description

Functions and methods that are exported from a module should have explicit return type and parameter type annotations. Missing type annotations at module boundaries make code contracts less clear and can negatively impact TypeScript's type inference performance in large codebases.

## Examples

Example of **incorrect** code:
```ts
// Missing return type void
export function test() {
  return;
}

// Missing return type string
export const arrowFn = () => 'test';

// Missing parameter type
export const processArg = (arg) => `test ${arg}`;

// 'any' type is not explicit enough
export const processAny = (arg: any) => `test ${arg}`;

export class Test {
  // Missing method return type
  method() {
    return;
  }
}
```

Example of **correct** code:
```ts
export function test(): void {
  return;
}

export const arrowFn = (): string => 'test';

export const processArg = (arg: string): string => `test ${arg}`;

export const processUnknown = (arg: unknown): string => `test ${arg}`;

export class Test {
  method(): void {
    return;
  }
}

// Non-exported functions don't need explicit types
function internal() {
  return;
}

// Valid for higher-order functions when configured
export const createHandler = () => (value: string): number => {
  return value.length;
};
```