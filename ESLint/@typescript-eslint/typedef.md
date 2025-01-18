Pattern: Missing type annotation

Issue: -

## Description

While TypeScript can infer many types automatically, some locations require explicit type annotations for type safety or code clarity. Inconsistent use of type annotations can make code harder to maintain, especially in places where type inference is unreliable or where explicit types improve code readability.

## Examples

Example of **incorrect** code:
```ts
// Missing parameter types
function format(input) {
  return input.toString();
}

// Missing member variable types
class User {
  name;
  role = 'user';
}

// Missing variable types
const items = [];
let value;

// Missing destructuring types
const [first, second] = pair;
const { id, title } = data;
```

Example of **correct** code:
```ts
// Explicit parameter types
function format(input: unknown): string {
  return input.toString();
}

// Explicit member types
class User {
  name: string;
  role: string = 'user';
}

// Explicit variable types
const items: string[] = [];
let value: number;

// Explicit destructuring types
const [first, second]: [number, number] = pair;
const { id, title }: Record<string, string> = data;
```