Pattern: Reference before declaration

Issue: -

## Description

Using variables, types, interfaces, or enums before they are declared can lead to confusion and potential runtime errors. This pattern makes code harder to read and understand as readers have to look ahead to understand what a reference means.

## Examples

Example of **incorrect** code:
```ts
// Variable use before declaration
console.log(myVar);
const myVar = 'value';

// Type use before declaration
const value: MyType = 'string';
type MyType = string;

// Enum use before declaration
const status = Status.Active;
enum Status {
  Active,
  Inactive
}
```

Example of **correct** code:
```ts
// Variable declared before use
const myVar = 'value';
console.log(myVar);

// Type declared before use
type MyType = string;
const value: MyType = 'string';

// Enum declared before use
enum Status {
  Active,
  Inactive
}
const status = Status.Active;
```