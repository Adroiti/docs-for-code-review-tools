Pattern: Verbose type assertion to non-null type

Issue: -

## Description

When asserting a nullable value to its non-null type, using the type assertion syntax (as or angle bracket) is more verbose than using the non-null assertion operator (!). The longer syntax is harder to maintain and can become outdated as types change.

## Examples

Example of **incorrect** code:
```ts
// Using type assertion
const value = maybeString as string;
const length = (str as string).length;

// Using angle bracket syntax
const name = <string>nullable;
const result = <Response>await request();

// Asserting in method call
const upper = (maybeString as string).toUpperCase();

// Multiple assertions
const nested = (obj as Interface1 as Interface2);
```

Example of **correct** code:
```ts
// Using non-null assertion
const value = maybeString!;
const length = str!.length;

// Single non-null assertion
const name = nullable!;
const result = (await request())!;

// Method call with non-null assertion
const upper = maybeString!.toUpperCase();

// Proper type narrowing
if (maybeString !== null) {
  const value = maybeString;
}

// Type guard usage
function isString(value: unknown): value is string {
  return typeof value === 'string';
}

if (isString(maybeString)) {
  const value = maybeString;
}
```