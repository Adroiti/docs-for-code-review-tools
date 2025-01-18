Pattern: Await usage on non-Thenable value

Issue: -

## Description

The await operator is meant for Thenable values (objects with a then method, like Promises). Using await on non-Thenable values causes unnecessary microtask delays and often indicates a programmer error, such as forgetting to call a function that returns a Promise.

## Examples

Example of **incorrect** code:
```ts
// Awaiting primitive values
await 'hello';
await 42;

// Awaiting non-async function result
const getData = () => 'data';
await getData();

// For-await on synchronous array
async function process() {
  const items = [1, 2, 3];
  for await (const item of items) {
    console.log(item);
  }
}

// Await using with synchronous disposable
function createSyncDisposable(): Disposable {
  return { [Symbol.dispose]() {} };
}
await using resource = createSyncDisposable();
```

Example of **correct** code:
```ts
// Awaiting Promise
await Promise.resolve('hello');

// Awaiting async function
const getData = async () => 'data';
await getData();

// Regular for-of for synchronous array
async function process() {
  const items = [1, 2, 3];
  for (const item of items) {
    console.log(item);
  }
}

// Await using with async disposable
function createAsyncDisposable(): AsyncDisposable {
  return { 
    async [Symbol.asyncDispose]() {} 
  };
}
await using resource = createAsyncDisposable();

// Regular using for sync disposable
using syncResource = createSyncDisposable();
```