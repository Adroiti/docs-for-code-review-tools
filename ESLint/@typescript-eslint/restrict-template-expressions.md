Pattern: Non-string type in template literal

Issue: -

## Description

Template literals automatically convert their expressions to strings, which can lead to unexpected results when the expressions aren't strings. Objects convert to `[object Object]`, arrays join their elements with commas without spaces, and other types may produce unfriendly string representations that make the output hard to read or use.

## Examples

Example of **incorrect** code:
```ts
const obj = { toString: () => 'custom' };
const arr = [1, 2, 3];

// Object produces [object Object]
const msg1 = `obj = ${{}}`; 

// Array joins with commas without spaces
const msg2 = `arr = ${arr}`;

// Boolean coercion may not be intended
const msg3 = `value = ${true}`;

// Number might need formatting
const msg4 = `price = ${0.1 + 0.2}`;
```

Example of **correct** code:
```ts
// Using string values
const str = 'hello';
const msg1 = `str = ${str}`;

// Explicitly converting/formatting values
const obj = { name: 'test' };
const msg2 = `obj = ${JSON.stringify(obj)}`;

const num = 0.1 + 0.2;
const msg3 = `price = ${num.toFixed(2)}`;

// Using string literals
const msg4 = `status = ${'ready'}`;

// Using template expressions for logs with commas
console.log('Values:', value1, value2);
```