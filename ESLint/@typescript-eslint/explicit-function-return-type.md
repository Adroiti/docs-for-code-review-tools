Pattern: Missing return type annotation in function

Issue: -

## Description

While TypeScript can infer function return types, missing explicit return type annotations can make code contracts less clear and impact type-checking performance in large codebases. Each function should clearly declare its return type to improve code readability and maintainability.

## Examples

Example of **incorrect** code:
```ts
// Return type void is implied
function process() {
  return;
}

// Return type is inferred as number
const calculate = function() {
  return 42;
};

// Return type is inferred as string
const getMessage = () => 'Hello';

class Service {
  // Method return type is implied
  getData() {
    return this.data;
  }
}

// Higher-order function without return type
const createHandler = () => (value) => {
  return value.length;
};
```

Example of **correct** code:
```ts
// Explicit void return type
function process(): void {
  return;
}

// Explicit number return type
const calculate = function(): number {
  return 42;
};

// Explicit string return type
const getMessage = (): string => 'Hello';

class Service {
  getData(): Data {
    return this.data;
  }
}

// Higher-order function with return types
const createHandler = (): (value: string) => number => {
  return (value: string): number => value.length;
};

// Function expression type is defined separately
type Handler = () => number;
const handler: Handler = () => 42;
```