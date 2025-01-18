Pattern: Non-Error throw value

Issue: -

## Description

Throwing values that are not Error objects loses the automatic stack trace and source location tracking that Error objects provide. Only throwing Error objects or instances of classes that extend Error ensures consistent error handling and debugging capabilities.

## Examples

Example of **incorrect** code:
```ts
throw 'error';

throw 0;

throw undefined;

throw null;

const err = new Error();
throw 'an ' + err;

const err = new Error();
throw `${err}`;

const err = '';
throw err;

function getError() {
  return '';
}
throw getError();
```

Example of **correct** code:
```ts
throw new Error();

throw new Error('error');

const e = new Error('error');
throw e;

try {
  throw new Error('error');
} catch (e) {
  throw e;
}

class CustomError extends Error {
  // ...
}
throw new CustomError();

function getError() {
  return new Error();
}
throw getError();
```