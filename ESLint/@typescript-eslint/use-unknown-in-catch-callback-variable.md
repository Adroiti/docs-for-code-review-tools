Pattern: Promise catch without unknown type

Issue: -

## Description

Leaving Promise rejection callbacks without an explicit `unknown` type allows potentially unsafe handling of errors. While TypeScript's `useUnknownInCatchVariables` compiler option enforces `unknown` for synchronous try-catch blocks, it doesn't affect Promise catch callbacks, making explicit type annotations necessary for type safety.

## Examples

Example of **incorrect** code:
```ts
// Implicit any type
Promise.reject(new Error('Fail'))
  .catch(err => {
    console.log(err.message);  // Unsafe access
  });

// Explicit any type
Promise.reject(new Error('Fail'))
  .catch((err: any) => {
    console.log(err.message);  // Still unsafe
  });

// Assuming specific error type
Promise.reject(new Error('Fail'))
  .catch((err: Error) => {
    console.log(err.message);  // Might not be Error
  });

// Error in then callback
somePromise.then(
  data => console.log(data),
  err => console.log(err)  // Implicit any
);
```

Example of **correct** code:
```ts
Promise.reject(new Error('Fail'))
  .catch((err: unknown) => {
    if (err instanceof Error) {
      console.log(err.message);  // Safe after check
    }
  });

somePromise.then(
  data => console.log(data),
  (err: unknown) => {
    // Type-safe error handling
    if (typeof err === 'string') {
      console.log(err.toUpperCase());
    }
  }
);
```