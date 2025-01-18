Pattern: Promise rejection with non-Error value

Issue: -

## Description

Rejecting a promise with a non-Error value loses the automatic stack trace and source location tracking that Error objects provide. Using Error objects (or classes extending Error) ensures consistent error handling and better debugging capabilities.

## Examples

Example of **incorrect** code:
```ts
Promise.reject('error');

const err = new Error();
Promise.reject('an ' + err);

new Promise((resolve, reject) => reject('error'));

new Promise((resolve, reject) => {
  const err = new Error();
  reject('an ' + err);
});
```

Example of **correct** code:
```ts
Promise.reject(new Error());

class CustomError extends Error {
  // ...
}
Promise.reject(new CustomError());

new Promise((resolve, reject) => reject(new Error()));

new Promise((resolve, reject) => {
  class CustomError extends Error {
    // ...
  }
  return reject(new CustomError());
});
```