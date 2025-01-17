Pattern: Unhandled Promise result

Issue: -

## Description

A floating (unhandled) Promise can lead to unexpected behavior, timing issues, and unhandled rejections. Any Promise-returning function should have its result handled through await, .then()/.catch() handlers, returned to caller, or explicitly marked as ignored with void operator.

## Examples

Example of **incorrect** code:
```ts
// Unhandled promise
asyncFunction();

// Incomplete error handling
promise.then(success => {
  // only handling success
});

// Missing error handler
promise.finally(() => {
  // cleanup without error handling
});

// Array of promises without Promise.all
async function processItems(items: number[]) {
  items.map(async item => process(item));
}

// Unhandled async arrow function
const handler = async () => {
  throw new Error('Failed');
};
element.onclick = handler;
```

Example of **correct** code:
```ts
// Using await
await asyncFunction();

// Complete error handling
promise.then(
  success => { /* handle success */ },
  error => { /* handle error */ }
);

// Proper catch handler
promise.catch(error => {
  // handle error
});

// Void operator for intentionally ignored promises
void asyncFunction();

// Returning promise to caller
async function processData() {
  return asyncFunction();
}

// Proper array promise handling
async function processItems(items: number[]) {
  await Promise.all(items.map(async item => process(item)));
}

// Error handler with finally
try {
  await riskyOperation();
} finally {
  // cleanup
}
```