Pattern: Non-generic Array constructor usage

Issue: -

## Description

Using the Array constructor without type parameters can lead to confusing behavior, as it may create arrays with unexpected length or content. The array literal syntax `[]` or typed Array constructor `Array<T>()` should be used instead.

## Examples

Example of **incorrect** code:
```ts
// Multi-argument constructor creates array with those elements
Array(1, 2, 3);
new Array(1, 2, 3);

// Single numeric argument creates sparse array of that length
Array(3);
new Array(3);
```

Example of **correct** code:
```ts
// Array literals
[1, 2, 3];
const items = [];

// Typed array constructors
new Array<string>();
Array<number>(1, 2, 3);

// Length constructor with explicit type
new Array<string>(3);

// Array from existing length
new Array(someArray.length);
```