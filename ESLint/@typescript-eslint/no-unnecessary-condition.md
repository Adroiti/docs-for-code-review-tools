Pattern: Unnecessary conditional check of type-proven value

Issue: -

## Description

Conditional checks on values that are proven by TypeScript's type system to be always truthy or always falsy are unnecessary and may indicate misunderstandings about the types. This includes conditions in if statements, ternaries, while loops, and logical operators that TypeScript can determine will always evaluate the same way.

## Examples

Example of **incorrect** code:
```ts
// Non-null array check
function processItems<T>(items: T[]) {
  if (items) {  // items can never be null
    items.forEach(item => process(item));
  }
}

// Known literal type check
function handleStatus(status: 'active' | 'inactive') {
  if (status) {  // status is never empty string
    console.log(status);
  }
}

// Optional chain on non-null
function getLength(str: string) {
  return str?.length;  // str is never null
}

// Boolean expression with known type
const arr = [1, 2, 3];
arr.filter(x => !!x);  // number is never falsy here

// Condition on never-null property
interface User {
  name: string;  // non-nullable
}
function printName(user: User) {
  if (user.name) {
    console.log(user.name);
  }
}
```

Example of **correct** code:
```ts
// Check for empty array
function processItems<T>(items: T[]) {
  if (items.length) {
    items.forEach(item => process(item));
  }
}

// Check specific status
function handleStatus(status: 'active' | 'inactive') {
  if (status === 'active') {
    console.log('Active');
  }
}

// Optional chain on nullable
function getLength(str: string | null) {
  return str?.length;
}

// Proper number filtering
const numbers = [0, 1, 2];
numbers.filter(x => x > 0);

// Check nullable property
interface User {
  name?: string;
}
function printName(user: User) {
  if (user.name) {
    console.log(user.name);
  }
}

// Type predicate when needed
function isString(value: unknown): value is string {
  return typeof value === 'string';
}
```