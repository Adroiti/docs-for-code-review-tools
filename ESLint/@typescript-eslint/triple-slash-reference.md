Pattern: Triple-slash reference directive

Issue: -

## Description

Using triple-slash reference directives (`/// <reference ... />`) is an outdated way to include types from other modules. Modern TypeScript code should use ES6-style imports for better maintainability, clearer dependencies, and better tooling support.

## Examples

Example of **incorrect** code:
```ts
/// <reference path="other-file.ts" />
/// <reference types="node" />
/// <reference lib="dom" />

export function doThing() {
  // Using types from referenced files
  const buffer: Buffer = Buffer.from([]);
  document.querySelector('div');
}
```

Example of **correct** code:
```ts
import { OtherType } from './other-file';
import type { Buffer } from 'node';

export function doThing() {
  // Using explicitly imported types
  const buffer: Buffer = Buffer.from([]);
}

// When reference is necessary, use import statements
declare global {
  interface Window {
    customProp: string;
  }
}
```