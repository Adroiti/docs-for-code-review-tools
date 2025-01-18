Pattern: Type parameter with single use

Issue: -

## Description

Type parameters should relate multiple parts of a type signature. A type parameter that appears only once is not relating anything and can be replaced with a simpler explicit type. Single-use type parameters make code harder to read and can potentially hide unsafe type assertions.

## Examples

Example of **incorrect** code:
```ts
function second<A, B>(a: A, b: B): B {
  return b;
}

function parseJSON<T>(input: string): T {
  return JSON.parse(input);
}

function printProperty<T, K extends keyof T>(obj: T, key: K) {
  console.log(obj[key]);
}
```

Example of **correct** code:
```ts
function second<B>(a: unknown, b: B): B {
  return b;
}

function parseJSON(input: string): unknown {
  return JSON.parse(input);
}

function printProperty<T>(obj: T, key: keyof T) {
  console.log(obj[key]);
}

// T appears twice: in the type of arg and as the return type
function identity<T>(arg: T): T {
  return arg;
}

// T appears twice: "keyof T" and in the inferred return type (T[K])
// K appears twice: "key: K" and in the inferred return type (T[K])
function getProperty<T, K extends keyof T>(obj: T, key: K) {
  return obj[key];
}
```