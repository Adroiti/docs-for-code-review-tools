Pattern: TypeScript directive comment suppressing type checks

Issue: -

## Description

TypeScript directive comments (@ts-expect-error, @ts-ignore, @ts-nocheck, @ts-check) allow bypassing the type system. Using these directives weakens TypeScript's effectiveness and often masks underlying type issues that should be properly fixed instead.

## Examples

Example of **incorrect** code:
```ts
// Suppressing without explanation
// @ts-ignore
const value = someFunc();

// Empty directive
if (false) {
  // @ts-expect-error
  console.log('hello');
}

// Suppressing an entire file
// @ts-nocheck

// Brief, unhelpful description
// @ts-expect-error: TODO
function example() {}
```

Example of **correct** code:
```ts
// Fix the actual type error
const value: string = someFunc();

// If suppression is necessary, provide detailed explanation
// @ts-expect-error: TS2532 - Object is potentially undefined, but we verify this earlier
const length = maybeString!.length;

// Use ts-check to enable rather than disable checks
// @ts-check
function example(x: number) {
  return x + 1;
}

// Detailed explanation of workaround
// @ts-expect-error: TS1234 because the library definition is missing this overload
someLibraryFunction('special-case');
```