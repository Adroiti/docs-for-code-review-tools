Pattern: Unused variable

Issue: -

## Description

Variables declared but never used increase code complexity and create confusion for readers. This includes TypeScript-specific unused declarations like types, interfaces, and generic parameters. Unused code should be removed to maintain cleaner, more maintainable codebases.

## Examples

Example of **incorrect** code:
```ts
// Unused variable
const x = 10;

// Unused parameter
function doSomething(unused: string) {
  console.log('Hello');
}

// Unused import
import { unused } from './module';

// Unused type parameter
function generic<T>() {
  console.log('No T used');
}
```

Example of **correct** code:
```ts
// Used variable
const x = 10;
console.log(x);

// Used parameter
function doSomething(used: string) {
  console.log(used);
}

// Used import
import { used } from './module';
console.log(used);

// Used type parameter
function generic<T>(value: T): T {
  return value;
}
```