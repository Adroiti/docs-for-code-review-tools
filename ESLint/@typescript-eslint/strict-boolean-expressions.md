Pattern: Unsafe type in boolean expression

Issue: -

## Description

Using non-boolean types in boolean expressions (conditions, logical operators, etc.) can lead to unexpected behavior due to implicit type coercion. Types like string, number, or object can have falsy values that make boolean checks unreliable, while nullable types require explicit null checks.

## Examples

Example of **incorrect** code:
```ts
// Nullable types without explicit checks
declare const num: number | undefined;
if (num) {
  console.log('num exists');
}

// String type coercion
declare const str: string;
if (!str) {
  console.log('str is empty');
}

// Object always truthy
let obj = {};
while (obj) {
  obj = getObj();
}

// Array predicates with non-boolean returns
['one', null].filter(x => x);
```

Example of **correct** code:
```ts
// Explicit null checks
let num: number | undefined;
if (num !== undefined) {
  console.log('num exists');
}

// Explicit string checks
let str: string;
if (str === '') {
  console.log('str is empty');
}

// Explicit boolean conversion
const arr = ['one', 'two'];
arr.filter(x => Boolean(x));

// Explicit comparisons
while (hasMore()) {
  obj = getObj();
}
```