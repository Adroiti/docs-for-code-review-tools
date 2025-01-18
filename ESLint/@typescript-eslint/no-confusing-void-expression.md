Pattern: Misplaced void expression in value position

Issue: -

## Description

A void expression represents a function call meant to be ignored, but using it in a value position (like assignment or return) creates confusing code. This can lead to programmer errors when void values are accidentally used where actual values are expected.

## Examples

Example of **incorrect** code:
```ts
// Storing void result in variable
const result = alert('Warning');

// Using void result in console
console.log(alert('Hello'));

// Returning void result
function logError() {
  return console.error('Failed');
}

// Chaining void promise
promise.then(value => window.postMessage(value));
```

Example of **correct** code:
```ts
// Void function in statement position
alert('Warning');

// Explicit void handling in promise
promise.then(value => {
  window.postMessage(value);
});

// Explicit return after void call
function logError() {
  console.error('Failed');
  return;
}

// Side effects in logical expressions
condition && console.log('True');
condition ? console.log('Yes') : console.log('No');

// Using void operator when intended
return void console.log('Done');
```