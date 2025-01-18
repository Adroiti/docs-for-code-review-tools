Pattern: Redundant empty export statement

Issue: -

## Description

An empty `export {}` statement is useful to turn a script file into a module file in TypeScript. However, when a file already contains other imports or exports, the empty export becomes redundant as the file is already treated as a module.

## Examples

Example of **incorrect** code:
```ts
export const value = 'Hello, world!';
export {};

// Also incorrect
import 'some-other-module';
export {};
```

Example of **correct** code:
```ts
export const value = 'Hello, world!';

// Also correct
import 'some-other-module';

// Empty export only when needed to make a module
export {};  // In a file with no other imports/exports
```