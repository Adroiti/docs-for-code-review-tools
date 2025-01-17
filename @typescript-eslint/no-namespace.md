Pattern: TypeScript namespace usage

Issue: -

## Description

TypeScript namespaces (formerly called "internal modules") are an outdated way to organize code. Modern TypeScript code should use ES2015 modules with import/export statements for better tooling support, tree shaking, and compatibility with the JavaScript ecosystem.

## Examples

Example of **incorrect** code:
```ts
// Using namespace keyword
namespace Validation {
  export interface StringValidator {
    isValid(s: string): boolean;
  }
  
  export class RegexValidator implements StringValidator {
    isValid(s: string): boolean {
      return true;
    }
  }
}

// Using module keyword (older syntax)
module Shipping {
  export interface Address {
    street: string;
    city: string;
  }
  
  export function validate(address: Address) {
    // ...
  }
}

// Nested namespaces
namespace App {
  namespace Models {
    export interface User {
      id: number;
      name: string;
    }
  }
}
```

Example of **correct** code:
```ts
// Using ES modules
export interface StringValidator {
  isValid(s: string): boolean;
}

export class RegexValidator implements StringValidator {
  isValid(s: string): boolean {
    return true;
  }
}

// Multiple exports
export interface Address {
  street: string;
  city: string;
}

export function validate(address: Address) {
  // ...
}

// Declare modules for external libraries
declare module 'external-lib' {
  export function helper(): void;
}

// Global augmentation in .d.ts files
declare global {
  interface Window {
    customProperty: string;
  }
}
```