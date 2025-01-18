Pattern: Non-null assertion operator usage

Issue: -

## Description

The non-null assertion operator (!) tells TypeScript to ignore potential null or undefined values. This bypasses TypeScript's type checking and can lead to runtime errors. Instead, code should be structured to handle potential null/undefined cases explicitly through type guards, optional chaining, or null checks.

## Examples

Example of **incorrect** code:
```ts
// Non-null assertion on nullable property
interface User {
  name?: string;
}
const user: User = {};
const name = user.name!;

// Non-null assertion in function call
function processUser(user: User | null) {
  console.log(user!.name);
}

// Non-null assertion in array access
const array: string[] | null = null;
array![0];

// Non-null assertion on method call
interface Service {
  getUser?: () => User;
}
const service: Service = {};
service.getUser!();
```

Example of **correct** code:
```ts
// Optional chaining and nullish coalescing
interface User {
  name?: string;
}
const user: User = {};
const name = user.name ?? 'default';

// Type guard
function processUser(user: User | null) {
  if (user !== null) {
    console.log(user.name);
  }
}

// Early return
function handleUser(user: User | null) {
  if (!user) return;
  console.log(user.name);
}

// Proper null checking
const array: string[] | null = null;
if (array) {
  console.log(array[0]);
}

// Optional chaining for method calls
interface Service {
  getUser?: () => User;
}
const service: Service = {};
service.getUser?.();
```