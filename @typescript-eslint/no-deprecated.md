Pattern: Usage of deprecated code element

Issue: -

## Description

Code marked with the JSDoc `@deprecated` tag indicates it should no longer be used, typically because a better alternative exists. Using deprecated code can lead to maintenance issues and may break in future versions.

## Examples

Example of **incorrect** code:
```ts
/** @deprecated Use fetchData() instead */
function getData() {
  return fetch('/api/data');
}

// Using deprecated function
await getData();

// Using Node.js deprecated API
import { parse } from 'node:url';
const url = parse('/foo');

/** @deprecated Use titleCase */
const uppercase = 'HELLO';
console.log(uppercase);
```

Example of **correct** code:
```ts
/** @deprecated Use fetchData() instead */
function getData() {
  return fetch('/api/data');
}

// Using recommended alternative
async function fetchData() {
  return fetch('/api/data');
}
await fetchData();

// Using modern URL API
const url = new URL('/foo', 'http://example.com');

/** @deprecated Use titleCase */
const uppercase = 'HELLO';
// Using non-deprecated alternative
const titleCase = 'Hello';
console.log(titleCase);
```