Pattern: Inconsistent spacing around type annotations

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent spacing around type annotations and type assertions in TypeScript, which can now be configured using the stylistic plugin's type-annotation-spacing rule.

## Examples

Example of **incorrect** code:
```ts
// Variable declarations
let foo:string;
const bar:number = 5;

// Function parameters and return types
function greet(name:string):string {}
class Example {
  constructor(value:number) {}
  method(param:string):void {}
}

// Type assertions
const value = expr as string;
const other = <number>expr;

// Type parameters
interface Generic<T=string> {}
type Container<T=object> = T;
```

Example of **correct** code:
```ts
// Variable declarations
let foo: string;
const bar: number = 5;

// Function parameters and return types
function greet(name: string): string {}
class Example {
  constructor(value: number) {}
  method(param: string): void {}
}

// Type assertions
const value = expr as string;
const other = <number>expr;

// Type parameters
interface Generic<T = string> {}
type Container<T = object> = T;
```

See [eslint.style](https://eslint.style) for the current version of this rule.