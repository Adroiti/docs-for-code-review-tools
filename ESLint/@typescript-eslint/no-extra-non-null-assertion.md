Pattern: Redundant non-null assertion operator

Issue: -

## Description

Multiple non-null assertion operators (`!`) on a single value serve no purpose as a single assertion is sufficient to tell TypeScript that a value's type excludes null and undefined. Additional assertions create unnecessary visual noise and potential confusion.

## Examples

Example of **incorrect** code:
```ts
// Multiple assertions on value access
const value = obj!!!.property;

// Multiple assertions on type assertion
function process(value: string | undefined) {
  return value!!! as string;
}

// Multiple assertions with optional chaining
function getName(obj?: { name: string }) {
  return obj!?.name;
}

// Multiple assertions in return
function getId(data: { id?: number }) {
  return data.id!!!;
}
```

Example of **correct** code:
```ts
// Single assertion when needed
const value = obj!.property;

// Single assertion for type narrowing
function process(value: string | undefined) {
  return value! as string;
}

// Optional chaining without assertion
function getName(obj?: { name: string }) {
  return obj?.name;
}

// Single assertion in return
function getId(data: { id?: number }) {
  return data.id!;
}

// No assertion when type is known
const definiteValue = obj.property;
```