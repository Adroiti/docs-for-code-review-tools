Pattern: Inconsistent space before function parenthesis

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent spacing before function parentheses, which can now be configured using the stylistic plugin's space-before-function-paren rule.

## Examples

Example of **incorrect** code:
```ts
// Regular functions
function foo () {}
function bar() {}

// Async functions
async function foo() {}
async function bar () {}

// Methods
class Example {
  method () {}
  async task() {}
}

// Arrow functions
const foo = (x: number) => {};
const bar = (x: number)=> {};

// Function types
interface Example {
  method (): void;
  callback: (x: string)=> void;
}
```

Example of **correct** code:
```ts
// No space style
function foo() {}
async function bar() {}

class Example {
  method() {}
  async task() {}
}

const foo = (x: number) => {};

interface Example {
  method(): void;
  callback: (x: string) => void;
}

// Or space style
function foo () {}
async function bar () {}

class Example {
  method () {}
  async task () {}
}
```

See [eslint.style](https://eslint.style) for the current version of this rule.