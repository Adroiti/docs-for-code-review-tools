Pattern: ts-ignore directive instead of ts-expect-error

Issue: -

## Description

Using `@ts-ignore` to suppress TypeScript errors is less safe than using `@ts-expect-error`. While both suppress errors, `@ts-expect-error` will cause an error if placed on a line that isn't actually erroring, preventing suppression comments from remaining in the code after the error they were suppressing has been fixed.

## Examples

Example of **incorrect** code:
```ts
// @ts-ignore
const str: string = 1;

/**
 * Explaining comment
 * @ts-ignore */
const multiLine: number = 'value';

/** @ts-ignore */
const block: string = 1;

// @ts-ignore: if key isn't in globalOptions it'll be undefined
const value = globalOptions[key];
```

Example of **correct** code:
```ts
// @ts-expect-error
const str: string = 1;

/**
 * Explaining comment
 * @ts-expect-error */
const multiLine: number = 'value';

/** @ts-expect-error */
const block: string = 1;

// @ts-expect-error: if key isn't in globalOptions it'll be undefined
const value = globalOptions[key];
```