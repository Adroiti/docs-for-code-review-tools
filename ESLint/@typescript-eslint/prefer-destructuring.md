Pattern: Direct property access over destructuring

Issue: -

## Description

Using direct property access instead of destructuring assignment can make code more verbose and less maintainable. This applies to both array indexing and object property access when the values could be destructured instead.

## Examples

Example of **incorrect** code:
```ts
const x = ['a'];
const y = x[0];

// Object property access without destructuring
const obj = { prop: 'value' };
const val = obj.prop;
```

Example of **correct** code:
```ts
const x = ['a'];
const [y] = x;

// Object property access with destructuring
const obj = { prop: 'value' };
const { prop: val } = obj;

// Direct access is ok when destructuring isn't possible
const x = { 0: 'a' };
const y = x[0];  // Object with numeric key can't use array destructuring
```